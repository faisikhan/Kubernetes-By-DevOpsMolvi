# Kubernetes on the VM

![image](https://user-images.githubusercontent.com/21220549/218764601-77bf10ec-15e9-4cad-9e76-781cb31ab315.png)

sed -i '/swap/d' /etc/fstab

The above command will remove the swap entry from /etc/fstab 

The following tutorial will help to install containerd.

https://www.itzgeek.com/how-tos/linux/ubuntu-how-tos/install-containerd-on-ubuntu-22-04.html

===>  kube-apiserver which is one of Kubernetes components uses port 6443 too.

The perfect article is here to install Kubernetes:

https://serverfault.com/questions/1118051/failed-to-run-kubelet-validate-service-connection-cri-v1-runtime-api-is-not-im

In case of any issues, follow the following link: https://stackoverflow.com/questions/62701490/kube-init-error-writing-crisocket-information-for-the-control-plane-node-timed

## Commands Summary from Containerd to Kubernetes

1. sudo apt-get update
2. sudo apt install apt-transport-https curl
3. sudo mkdir -p /etc/apt/keyrings
4. curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
5. echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null.
6. sudo apt-get update
7. sudo apt-get install containerd.io
8. sudo mkdir -p /etc/containerd
9. sudo containerd config default | sudo tee /etc/containerd/config.toml
10. sudo nano /etc/containerd/config.toml [set SystemdCgroup = true]
11. sudo systemctl restart containerd
12. curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add
13. sudo apt-add-repository "deb http://apt.kubernetes.io/ kubernetes-xenial main"
14. sudo apt install kubeadm kubelet kubectl kubernetes-cni
15. swapoff -a
16. nano /etc/fstab
17. modprobe br_netfilter
18. nano /proc/sys/net/ipv4/ip_forward [Edit entry in ip_forward file and change to 1 like sysctl -w net.ipv4.ip_forward=1]
19. kubeadm init

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




