# Google Kubernetes Engine

Google Kubernetes Engine (GKE) is a managed Kubernetes service that allows users to deploy and operate containerized applications using Google's infrastructure. It is pretty quick
to get started with GKE on Goolge Cloud Platform. We can sign up for a free tier and we can get our hands on GKE.

You can follow the following basic steps to create a Managed Kubernetes Cluster on Google Cloud Platform using the Google Kubernetes Engine.

### 1. Create a Kubernetes Cluster:

![image](https://user-images.githubusercontent.com/21220549/208852432-6fbd8328-3566-4d20-91ad-786936263c74.png)

If we select Zonal, the control plane [which manages the worker nodes and the Pods in the cluster] and nodes run in a single zone. We can select more replica zones, however, 
it'll increase the costs. 

Cluster region can not be changed once its created. By default, a regional cluster replicates the control plane and worker nodes across three zones.

A node pools is a group of VMs, servers we can say in the same zone. In a single node pool, the number of nodes can be increased or decreased depending on the workload.

![image](https://user-images.githubusercontent.com/21220549/208858664-b5b5b9c0-50c6-49be-9277-6fa75d172a80.png)

**With the default maximum of 110 Pods per node for Standard clusters, Kubernetes assigns a /24 CIDR block (256 addresses) to each of the nodes.**

![image](https://user-images.githubusercontent.com/21220549/208859009-c2f96986-fe95-4aa6-bce4-c96450da375f.png)

The cluster has been created with 3-nodes in one zone.

![image](https://user-images.githubusercontent.com/21220549/208883877-588d77ff-af39-4d37-8d4e-fd68632ba3a6.png)

We can see that the control plane node and the worker nodes are in the same zone. 

### 2. Connect with a Pod

Go to the kubectl option, you will see the exec ====> nginx-1. We will be connected to the pod.

![image](https://user-images.githubusercontent.com/21220549/208887844-5858d393-cc24-40b7-8f43-53786efef183.png)
