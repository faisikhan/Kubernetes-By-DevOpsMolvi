# Kubectl Commands Cheat Sheet- Part B

Kubectl is a command-line tool that allows users to interact with Kubernetes clusters. Kubectl is used to deploy applications, manage & monitor cluster resources.

1. `kubectl config view` ==> Lists all clusters for which kubeconfig entries have been generated
2. `kubectl exec -it elasticsearch-0 -- /bin/bash` ==> Connect with elasticsearch-0 pod using SSH.
3. `kubectl delete pods --all -n devopsmolvi-elasticsearch --force` ==> Deletes all pods forcefully in the devopsmolvi-elasticsearch namespace.
4. `kubectl delete statefulsets es-cluster --namespace=devopsmolvi-elasticsearch` ==> The StatefulSet es-cluster will be deleted from the devopsmolvi-elasticsearch namespace.
5. `kubectl rollout status sts/es-cluster --namespace=devopsmolvi-elasticsearch` ==> It checks the rollout progress and status of the StatefulSet named es-cluster in the devopsmolvi-elasticsearch namespace.
6. `kubectl get pvc -n devopsmolvi-elasticsearch` ==> Get the information about PersistentVolumeClaims (PVCs) in devopsmolvi-elasticsearch namespace.
7. `kubectl get all --all-namespaces -o yaml > all-resources.yaml` ==> Retrieves the information of all resources in all namespaces and saves the output in all-resources.yaml file.
8. `kubectl get svc -n devopsmolvi-elasticsearch` ==> Gets the information about services in the devopsmolvi-elasticsearch namespace.
9. `kubectl describe svc -n devopsmolvi-elasticsearch my-es-service` ==> It will share more details about the "my-es-service" service.
10. `kubectl apply -f es-main-cluster.yaml -n devopsmolvi-elasticsearch` ==> It will apply the configuration specified in the es-main-cluster.yaml file.
11. `watch kubectl get pods -n devopsmolvi-elasticsearch` ==> This command is used to monitor the pods after their deployment. 



