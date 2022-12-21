# Kubernetes

1. One of the most popular tools for container orchestration.
2. A node means a server in Kubernetes.
3. A cluster means a number of servers coupled together. In Kubernetes, there should be at least 2 nodes in a cluster:

**i.  Master Node**
It is the main node in Kubernetes which does the administration part, it runs **kubeadm**. Kubeadm performs the actions necessary to get a minimum viable cluster up and running quickly. 

**ii. Worker Node**
Worker nodes are servers that run the workloads. Workload means containerized apps running in the production.

## Control Plane

In simple words, the Kubernetes API Server is known as the Control Plane.

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

A node pools is a group of VMs, servers we can say in the same zone. In a single node pool, the number of nodes can be increased or decreased depending on the workload.

![image](https://user-images.githubusercontent.com/21220549/208858664-b5b5b9c0-50c6-49be-9277-6fa75d172a80.png)

**With the default maximum of 110 Pods per node for Standard clusters, Kubernetes assigns a /24 CIDR block (256 addresses) to each of the nodes.**

![image](https://user-images.githubusercontent.com/21220549/208859009-c2f96986-fe95-4aa6-bce4-c96450da375f.png)

The cluster has been created with 3-nodes in one zone.

![image](https://user-images.githubusercontent.com/21220549/208883877-588d77ff-af39-4d37-8d4e-fd68632ba3a6.png)

We can see that the control plane node and the worker nodes are in the same zone. 

## Attach to a Pod

Go to the kubectl option, you will see the exec ====> nginx-1. We will be connected to the pod.

![image](https://user-images.githubusercontent.com/21220549/208887844-5858d393-cc24-40b7-8f43-53786efef183.png)
