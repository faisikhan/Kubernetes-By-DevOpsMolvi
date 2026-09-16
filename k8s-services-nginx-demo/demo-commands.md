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
