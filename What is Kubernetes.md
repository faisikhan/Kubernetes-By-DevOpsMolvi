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

## Google Docs

If you want to download the lectures in the PDF format, here are the Google Drive Links:
1. K8s Cluster Deep Dive: https://docs.google.com/presentation/d/1AaMttCRap-j1NwC8d6wWeXzOTKY0YI6ZtyAKwu6ZsIg/edit?usp=sharing
2. Kubernetes Terminology: https://docs.google.com/presentation/d/1m1ab6W8Z0-iTukfqvHnwEx5ijwVLiAueuzc6ybSa5bg/edit?usp=sharing


## Kubernetes

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

## Kubernetes Manifests

Kubernetes manifests are configuration files that describe the desired state of objects in a Kubernetes cluster. They are written in YAML.

After the successful installation of Kubernetes cluster, you can find this directory on the master node/control plane.

`/etc/kubernetes/manifests`

`-rw------- 1 root root 2392 Dec 19 04:02 etcd.yaml`

`-rw------- 1 root root 4009 Dec 19 04:02 kube-apiserver.yaml`

`-rw------- 1 root root 3520 Dec 19 04:02 kube-controller-manager.yaml`

`-rw------- 1 root root 1440 Dec 19 04:02 kube-scheduler.yaml`
