# How to Create a Kubernetes Cluster

It is one of my favorite guide in which we are going to create a Kubernetes ourselves on a couple of Virtual Machines on our AWS account.

In this Kubernetes Cluster, we'll have:

1. One Master Node/Control Plane [8GB RAM, 2 CPUs]
2. One Worker Node [4GB RAM, 1 CPU each]

It is upto you, if you want to have one master and more worker nodes.

In the beginning, I'll have one master & one worker node and we'll learn how we can join the worker node with the master node.


### Step No.1 VPC on AWS

1. First of all, we need to create a Virtual Private Cloud where we'll run all our VMs.
2. We'll create a security group in that VPC.
3. We've to allow the following ports in our security group 6443 for Kube-API server.


### Step No.2 Create EC2 VMs

1. We'll create 3 VMs in total, one VM would be our Master Node and the rest would be Worker Nodes.
2. The VMs must be created in the same VPC that we created above and the same security group.

### Install Containerd on the Master Node 

Containerd is the Container Runtime just like we have Docker or Podman and it is used to run containers in the Pods. So we are going to proceed with the installation of Containered.

Now there is really a very important concept that we must know about Swap memory and we have to disable it. The reason of disabling swap memory is that Kubernetes relies on predictable memory usage for scheduling pods efficiently, and swap can make it difficult to accurately calculate the memory requirements of a pod. Therefore, it is recommended to disable to the swap memory to avoid any performance degradation issues.

Run the following command to remove the swap entry.

`sed -i '/swap/d' /etc/fstab`

The above command will remove the swap entry from /etc/fstab as you can see the following image:

![image](https://user-images.githubusercontent.com/21220549/218764601-77bf10ec-15e9-4cad-9e76-781cb31ab315.png)

After that we need to run the following commands to install Containerd:

1. `sudo apt-get update`
2. `sudo apt install apt-transport-https curl`
3. `sudo mkdir -p /etc/apt/keyrings`
4. `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg`
5. `echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null.`
6. `sudo apt-get update`
7. `sudo apt-get install containerd.io`
8. `sudo mkdir -p /etc/containerd`
9. `sudo containerd config default | sudo tee /etc/containerd/config.toml`
10. `sudo nano /etc/containerd/config.toml [set SystemdCgroup = true]`
11. `sudo systemctl restart containerd`


The purpose of setting SystemdCgroup = true in the config.toml file of containerd is to enable the use of systemd for managing cgroups (control groups) for containers.

Containered Should be Installed Now....


### Install Kubernetes [kubeadm, kubelet, kubectl]

13. `curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.30/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg`
14. `echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.30/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list`
15. `sudo apt update`
16. `sudo apt install -y kubelet kubeadm kubectl`
17. `sudo apt-mark hold kubelet kubeadm kubectl`
18. `modprobe br_netfilter`
19. `cat <<EOF | sudo tee /etc/sysctl.d/k8s.conf`

`net.bridge.bridge-nf-call-iptables  = 1`

`net.bridge.bridge-nf-call-ip6tables = 1`

`net.ipv4.ip_forward                 = 1`

`EOF`
21. `sysctl --system`
22.  `kubeadm init --pod-network-cidr=10.0.0.0/16`

### KubeConfig Setup

22. mkdir -p $HOME/.kube
23. sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
24. sudo chown $(id -u):$(id -g) $HOME/.kube/config
25. export KUBECONFIG=/path/to/cluster-config

### Install Flannel Network Plugin

Flannel is an open-source Container Network Interface (CNI) plugin that creates a virtual network for containers.

26. kubectl apply -f https://github.com/flannel-io/flannel/releases/latest/download/kube-flannel.yml

### Kubectl autocomplete

Execute the following commands for kubectl autocomplete. It is strongly recommended for quick learning.

1. source <(kubectl completion bash)
2. echo "source <(kubectl completion bash)" >> ~/.bashrc
3. alias k=kubectl
4. complete -o default -F __start_kubectl k
5. kubectl -A        ===========>    Used for appending --all-namespaces.
