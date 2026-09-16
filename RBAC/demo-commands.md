# Apply everything

```
kubectl apply -f serviceaccount.yaml
kubectl apply -f role.yaml
kubectl apply -f rolebinding.yaml
kubectl apply -f clusterrole.yaml
kubectl apply -f clusterrolebinding.yaml
```

# Verify permissions (as the ServiceAccount)

```
kubectl auth can-i get pods --as=system:serviceaccount:default:pod-reader-sa
kubectl auth can-i list pods --as=system:serviceaccount:default:pod-reader-sa
kubectl auth can-i delete pods --as=system:serviceaccount:default:pod-reader-sa
# ^^ the commands should give the output as NO

kubectl auth can-i list nodes --as=system:serviceaccount:default:pod-reader-sa

# ^ the command should give the output as YES
```

# Inspect
```
kubectl get roles,rolebindings -n default
kubectl get clusterroles,clusterrolebindings | grep pod-reader
```

# Cleanup

```
kubectl delete -f clusterrolebinding.yaml
kubectl delete -f clusterrole.yaml
kubectl delete -f rolebinding.yaml
kubectl delete -f role.yaml
kubectl delete -f serviceaccount.yaml
````
