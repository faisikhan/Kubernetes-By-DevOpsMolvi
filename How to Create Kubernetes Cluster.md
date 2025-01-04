# How to Create a Kubernetes Cluster

It is one of my favorite guide in which we are going to create a Kubernetes ourselves on a couple of Virtual Machines on our AWS account.

In this Kubernetes Cluster, we'll have:

1. One Master Node/Control Plane [8GB RAM, 2 CPUs]
2. Two Worker Nodes [4GB RAM, 1 CPU each]

It is upto you, if you want to have one master and one worker nodes.

In the beginning, I'll have one master & one worker nodes and I'll join the 2nd worker node later so we can learn, how we can join additional worker nodes.


### Step No.1 VPC on AWS

1. First of all, we need to create a Virtual Private Cloud where we'll run all our VMs.
2. We'll create a security group in that VPC.
3. We've to allow the following ports in our security group 6443 for Kube-API server.


### Step No.2 Create EC2 VMs

1. We'll create 3 VMs in total, one VM would be our Master Node and the rest would be Worker Nodes.
2. The VMs must be created in the same VPC that we created above and the same security group.

### Install Containerd on the Master Node 

Containerd is the Container Runtime just like we have Docker or Podman and it is used to run containers in the Pods. So we are going to proceed with the installation of Containered.

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

===
Containered Should be Installed Now
===

### Install Kubernetes [kubeadm, kubelet, kubectl]

13. `curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.30/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg`
14. `echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.30/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list`
15. `sudo apt update`
16. `sudo apt install -y kubelet kubeadm kubectl`
17. `sudo apt-mark hold kubelet kubeadm kubectl`
18. `modprobe br_netfilter`
19. `nano /proc/sys/net/ipv4/ip_forward [Edit entry in ip_forward file and change to 1 like sysctl -w net.ipv4.ip_forward=1]`
20. `kubeadm init`

![image](https://user-images.githubusercontent.com/21220549/221897582-a3a1fa58-fee1-40f1-8b71-c120a13928ce.png)

This is for services to be accessible on my local windows system:
![image](https://user-images.githubusercontent.com/21220549/222120187-937e3868-f39e-4837-929c-3ad141a3db5c.png)

20. In order to list all the pods on master node:

kubectl get pods --all-namespaces

![image](https://user-images.githubusercontent.com/21220549/222126970-e70a4270-5c52-41b2-a37b-164a42ff5890.png)

![image](https://user-images.githubusercontent.com/21220549/222368243-5afde9e1-97ff-4173-adb4-8405d661e12b.png)

21. kubectl get nodes -o wide
22. kubectl get pods --all-namespaces -o wide

![image](https://user-images.githubusercontent.com/21220549/222374135-e2fc6717-06ad-4d4e-bd5c-0b19e03eefca.png)

23. Create a simple Nginx pod with the following command:
kubectl run nginx --image=nginx --restart=Never

24. kubectl describe pod nginx        ===========>    It will show the details of our pod.

## Kubectl autocomplete

Execute the following commands for kubectl autocomplete. It is strongly recommended for quick learning.

1. source <(kubectl completion bash)
2. echo "source <(kubectl completion bash)" >> ~/.bashrc
3. alias k=kubectl
4. complete -o default -F __start_kubectl k
5. kubectl -A        ===========>    Used for appending --all-namespaces.

![image](https://user-images.githubusercontent.com/21220549/223702236-5d84944e-15d1-4ad1-91c1-aa7746585e63.png)
