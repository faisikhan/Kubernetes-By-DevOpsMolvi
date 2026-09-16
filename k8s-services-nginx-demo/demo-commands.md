kubectl apply -f clusterip-service.yaml
kubectl get svc
kubectl describe svc nginx-clusterip
kubectl run tmp-curl --image=curlimages/curl -it --rm -- curl http://nginx-clusterip
