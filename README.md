# Kubernetes

1. One of the most popular tools for container orchestration.
2. A node means a server in Kubernetes.
3. A cluster means a number of servers coupled together. In Kubernetes, there should be at least 2 nodes in a cluster:

**i.  Master Node**
It is the main node in Kubernetes which does the administration part, it runs **kubeadm**. Kubeadm performs the actions necessary to get a minimum viable cluster up and running quickly. 

**ii. Worker Node**
Worker nodes are servers that run the workloads. Workload means containerized apps running in the production.

Good tutorial to install Kubernetes on Ubuntu:
https://www.cloudsigma.com/how-to-install-and-use-kubernetes-on-ubuntu-20-04/

## kubelet

It is the main agent used for communication among the nodes, it should be installed on the master and all worker nodes.

## kubeadm

Simply we can say, it is the Kubernetes system administrator. It initializes and administer the cluster.

## kubectl

It is a Kubernetes tool that allows users to run the commands inside the Kubernetes clusters.

## kubernetes-cni

A Kubernetes tool for containers network and data exchange.

1. Create a Kubernetes Cluster:

![image](https://user-images.githubusercontent.com/21220549/208852432-6fbd8328-3566-4d20-91ad-786936263c74.png)

If we select Zonal, the control plane [which manages the worker nodes and the Pods in the cluster] and nodes run in a single zone. We can select more replica zones, however, it'll increase the costs. 

Cluster region can not be changed once its created. By default, a regional cluster replicates the control plane and worker nodes across three zones.
