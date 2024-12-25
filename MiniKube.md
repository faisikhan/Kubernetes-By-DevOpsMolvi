# **How to Install Minikube? A Beginners Guide for DevOps Engineers**

# What is Minikube?

Minikube is a tool that allows you to run Kubernetes clusters locally for development and testing purposes. We can install Minikube on our Local VM or on a server in the cloud. Before proceeding, we need to make sure Docker is installed on the virtual machine.

You can watch the following tutorial to install Docker: https://youtu.be/r65dUVXULT4

Now in order to install Minikube, run the following commands:

`curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`

`sudo install minikube-linux-amd64 /usr/local/bin/minikube`

`minikube version`

# How to start Minikube with Docker Driver?

`minikube start --driver=docker`

`minikube start --driver=docker --force`

`minikube status`

`sudo snap install kubectl --classic`

`kubectl version --client`

The Minikube is installed :)

# How to Install kubectl?

The kubectl is a CLI used to interact with Kubernetes Clusters. We will use it to work with our Minikube Cluster. The installation of kubectl is really simple and we need to execute the following commands to install it.

`sudo apt install -y apt-transport-https ca-certificates curl`

`curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -`

`echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list`

# Running few kubectl commands

`kubectl cluster-info`

`kubectl config view`

`kubectl get nodes`

`kubectl get pods`

# Deploy NGINX web server on Minikube

`kubectl create deployment devops-web --image=nginx:latest`

`kubectl get deployment`

`kubectl get pods`

