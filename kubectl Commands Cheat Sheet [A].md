# 50 Most Frequently Used kubectl commands for DevOps Engineers [Part A]

Kubectl is a command-line tool that allows users to interact with Kubernetes clusters. Kubectl is used to deploy applications, manage & monitor cluster resources.


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
23. `kubectl run new-pod --image=alpine:latest` ==> Run a new pod with an image of your choice.
24. `kubectl delete pod new-pod` ==> Delete a pod.
25. `kubectl get deployments` ==> See deployments of a namespace.
26. `kubectl get deployments --all-namespaces` ==> See all deployments in all namespaces.
27. `kubectl scale deployment deployment-name -n namespace-name --replicas=3` => Scale up a deployment upto 3 pods.
28. `kubectl delete deployment deployment-name` ==> Delete a deployment.
29. `kubectl get services` ==> List services in the default namespace.
30. `kubectl get services --all-namespaces` ==> Services running in all namespaces.
31. `kubectl create service loadbalancer new-loadbalancer-service --tcp=80:8080` ==> It'll create a new loadbalancer service that exposes port 80 & routes traffic to container port 8080.
32. `kubectl describe service new-loadbalancer-service` ==> Describes a service and shares more details.
33. `kubectl delete service new-loadbalancer-service` ==> Deletes a service.
34. `kubectl get configmaps` ==> Lists down configmaps of the default namespace.
35. `kubectl get configmaps --all-namespaces` ==> Lists all Configmaps in all namespaces of the cluster.
36. `kubectl describe configmap my-configmap -n namespace` ==> See the details of a configmap in a specific namespace.
37. `kubectl delete configmap my-configmap` ==> Delete a configmap.
38. `kubectl get secrets` ==> The secrets of our K8s cluster.
39. `kubectl get secrets --all-namespaces` ==> Secrets in all namespaces of a cluster.
40. `kubectl create secret generic my-secret --from-literal=username=admin --from-literal=password=admin123` ==> It'll create a new secret.
41. `kubectl describe secret my-secret` ==> Details of our secret.
42. `kubectl delete secret my-secret` ==> It will delete the secret.
43. `kubectl delete all --all --namespace=my-namespace` ==> It will delete all resources in "my-namespace".
44. `kubectl get pods --watch --all-namespaces` ==> Continuously monitor the status of pods in all namespaces.
45. `kubectl get pods -A` ==> See pods in all namespaces, instead of using --all-namespaces, we can use -A as well.
46. `kubectl get replicasets --all-namespaces` ==> Replicasets in all namespaces.
47. `kubectl get daemonsets --all-namespaces` ==> Daemonsets in all namespaces.
48. `kubectl get statefulsets --all-namespaces` ==> Statefulsets in all namespaces.
49. `kubectl top nodes` ==> Get resource utilization of nodes.
50. `kubectl top pods` ==> Get resource utilization of pods.
