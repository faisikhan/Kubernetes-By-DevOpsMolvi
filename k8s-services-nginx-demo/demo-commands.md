## ClusterIP Lab Commands

```
kubectl apply -f clusterip-service.yaml
kubectl get svc
kubectl describe svc nginx-clusterip

# Test from inside the cluster (spin up a temp pod with curl)
kubectl run tmp-curl --image=curlimages/curl -it --rm -- curl http://nginx-clusterip
```

## NodePort Lab Commands

```
kubectl apply -f nodeport-service.yaml
kubectl get svc nginx-nodeport

# Minikube-specific — get accessible URL directly
minikube service nginx-nodeport --url

# Or manually
minikube ip
curl http://<minikube-ip>:30080
```
## Load Balancer Lab Commands

```
kubectl apply -f loadbalancer-service.yaml
kubectl get svc nginx-loadbalancer   # EXTERNAL-IP will show <pending> on Minikube, keep that in mind

# Minikube workaround to simulate LoadBalancer behavior

minikube tunnel   # run in a separate terminal, keep it open
kubectl get svc nginx-loadbalancer   # now shows an external IP

# DNS Resolution

kubectl run tmp-curl --image=curlimages/curl -it --rm -- curl http://nginx-clusterip.default.svc.cluster.local 

```
