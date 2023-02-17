# Kubernetes on the VM

![image](https://user-images.githubusercontent.com/21220549/218764601-77bf10ec-15e9-4cad-9e76-781cb31ab315.png)

sed -i '/swap/d' /etc/fstab

The above command will remove the swap entry from /etc/fstab 

## Install Containerd

The following tutorial will help to install containerd.

https://www.itzgeek.com/how-tos/linux/ubuntu-how-tos/install-containerd-on-ubuntu-22-04.html

===>  kube-apiserver which is one of Kubernetes components uses port 6443 too.

