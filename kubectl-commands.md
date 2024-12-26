# 50 Most Frequently Used kubectl commands for DevOps Engineers

1. `kubectl help` ==> to get help and more information about any command.
2. `kubectl cluster-info` ==> shares the K8s cluster information.
3. `kubectl cluster-info dump` ==> for troubleshooting K8s cluster issues, we'll get logs.
4. `kubectl get nodes` ==> lists all nodes of the cluster.
5. `kubectl describe node <node_name>` ==> get all the details about a specific node, change the node name.
6. `kubectl version` ==> the version of kubectl client, server and kustomize.
7. `kubectl get all` ==> overview of all resources on the cluster like pods, deployments or services etc.
8. `kubectl options` ==> Prints the kubectl command options that can be used with kubectl command.
9. `kubectl api-resources` ==> Prints all the supported API resources on the server.
10. `kubectl api-versions` ==> Prints all the supported API versions on the server.
11. `kubectl get namespaces` ==> Lists all namespaces on the cluster.
12. `kubectl create namespace new-namespace` ==> It will create a new namespace.
13. `kubectl config set-context --current --namespace=new-namespace` ==> Set the default namespace as the new-namespace.
14. `kubectl delete namespace new-namespace` ==> Delete the namespace.
15. `kubectl get pods` ==> List pods in the default namespace.
16. `kubectl get pods -n namespace_name` ==> List pods of a specific namespace.
17. `kubectl get pods --all-namespaces` ==> Lists pods of all namespaces.
18. `kubectl get pods -o wide` ==> Lists pods with more details.
19. `kubectl describe pod new-pod` ==> More details of a pod.
20. `kubectl logs new-pod` ==> Shares logs of a pod.
21. `kubectl logs -f new-pod` ==> Live or stream logs of a pod.
22. `kubectl exec -it <pod-name> -- /bin/bash` ==> Access a pod using SSH.
23. `kubectl run new-pod --image=alpine:latest ==> Run a new pod with an image of your choice.
24. `kubectl delete pod new-pod` ==> Delete a pod.
25. `kubectl get deployments` ==> See deployments of a namespace.
26. `kubectl get deployments --all-namespaces` ==> See all deployments in all namespaces.
27. `kubectl scale deployment deployment-name -n namespace-name --replicas=3` => Scale up a deployment, there will be 3 pods of that deployment.
28. `kubectl delete deployment deployment-name` ==> Delete a deployment.
