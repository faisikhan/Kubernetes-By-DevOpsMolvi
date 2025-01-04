# Welcome to Kubernetes by DevOps Molvi

This repository will have all the Kubernetes learning material that we'll discuss and learn together on my DevOps Molvi YouTube channel.

By the way, I'll explain Kubernetes here but if you want to watch my Kubernetes Lectures, I'll list them out here:

1. What is Kubernetes- https://youtu.be/iznUPUHChEc
2. What is K8s Used for- https://youtu.be/ma6_i4XMYEc
3. Kubernetes Architecture- https://youtu.be/gSGMD7X0neQ
4. Kubernetes Cluster Deep Dive- https://youtu.be/LgmN3bDITwE
5. Kubernetes Terminology- https://youtu.be/3wC7-cMUYDk
6. How to Install MiniKube- https://youtu.be/DSNEBqLFLrk
7. kubectl commands cheat sheet- https://youtu.be/9ROeiqi3UOQ

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

## kubelet

It is the main agent used for communication among the nodes, it should be installed on the master and all worker nodes.

## kubeadm

Simply we can say, it is the Kubernetes system administrator. It initializes and administer the cluster.

## kubectl

It is a Kubernetes tool that allows users to run the commands inside the Kubernetes clusters. It communicates with your API server. It can not modify or change the cluster settings. 

## kubernetes-cni

A Kubernetes tool for containers network and data exchange.


![image](https://github.com/faisikhan/kubernetes/assets/21220549/94469fda-160b-4e89-ab9f-fc839112054b)



## Kubernetes Manifests

/etc/kubernetes/manifests

-rw------- 1 root root 2392 Dec 19 04:02 etcd.yaml
-rw------- 1 root root 4009 Dec 19 04:02 kube-apiserver.yaml
-rw------- 1 root root 3520 Dec 19 04:02 kube-controller-manager.yaml
-rw------- 1 root root 1440 Dec 19 04:02 kube-scheduler.yaml

1. kubectl config view
2. kubectl get pods
3. kubectl get pods my-pod-name
4. kubectl get nodes  

![image](https://user-images.githubusercontent.com/21220549/208919735-bcd954e3-4c6d-448a-8973-470df9c9f424.png)

1. kubectl create deployment my-deployment --image nginx:latest --port 8088    =============> A new deployment will be created with one replicaset.
2. kubectl get deployment
3. kubectl describe deployment my-deployment

![image](https://user-images.githubusercontent.com/21220549/208929979-579094e5-955c-46bf-8ceb-d8d6b3faadb9.png)

4. kubectl delete deployment my-deployment    =============> It will delete the deployment.
