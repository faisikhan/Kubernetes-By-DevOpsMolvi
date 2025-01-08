# Kubectl Commands Cheat Sheet- Part B

Kubectl is a command-line tool that allows users to interact with Kubernetes clusters. Kubectl is used to deploy applications, manage & monitor cluster resources.

1. `kubectl config view` ==> To view your current Kubernetes configurations.
2. `kubectl exec -it es-cluster-0 -- /bin/bash` ==> Connect with elasticsearch-0 pod using SSH.
3. `kubectl delete pods --all -n devopsmolvi-elasticsearch --force` ==> Deletes all pods forcefully in the devopsmolvi-elasticsearch namespace.
4. `kubectl delete statefulsets es-cluster --namespace=devopsmolvi-elasticsearch` ==> The StatefulSet es-cluster will be deleted from the devopsmolvi-elasticsearch namespace.
5. `kubectl rollout status sts/es-cluster --namespace=devopsmolvi-elasticsearch` ==> It checks the rollout progress and status of the StatefulSet named es-cluster in the devopsmolvi-elasticsearch namespace.
6. `kubectl get pvc -n devopsmolvi-elasticsearch` ==> Get the information about PersistentVolumeClaims (PVCs) in devopsmolvi-elasticsearch namespace.
7. `kubectl get all --all-namespaces -o yaml > all-resources.yaml` ==> Retrieves the information of all resources in all namespaces and saves the output in all-resources.yaml file.
8. `kubectl get svc -n devopsmolvi-elasticsearch` ==> Gets the information about services in the devopsmolvi-elasticsearch namespace.
9. `kubectl describe svc -n devopsmolvi-elasticsearch es-cluster` ==> It will share more details about the "my-es-service" service.
10. `kubectl apply -f es-main-cluster.yaml -n devopsmolvi-elasticsearch` ==> It will apply the configuration specified in the es-main-cluster.yaml file.
11. `watch kubectl get pods -n devopsmolvi-elasticsearch` ==> This command is used to monitor the pods after their deployment.
12. `kubectl scale statefulset es-cluster --replicas=3` ==> It will scale up the statefulset to 3 replicas.
13. `kubectl get sc` ==> Lists the type of the storage class like for example, standard.
14. `kubectl describe storageclass standard` ==> To see the details of the standard storage class.
15. `kubectl get pv` ==> pv stands for PersistenVolumes and this command lists all persistent volumes.
16. `kubectl describe pv my-pv-name` ==> We'll get more details about the Persistent Volume.
17. `kubectl get pv my-pv-name -o wide` ==> It'll share some more details about the volume.
18. `kubectl get pv my-pv-name -o json` ==> This command will share the output of the PersistentVolume in JSON format.
19. `kubectl get pv my-pv-name -o yaml | grep -i storageClass` ==> Shares the storage class of the volume.
20. `kubectl edit pv my-pv-name` ==> If we want to modify the volume specifications.
21. `kubectl edit pv` ==> We can edit all Persistent Volumes at once, the changes effect immediately after saving.
22. `kubectl delete pv my-pv-name` ==> It'll delete the volume, we have to give the name of the volume.
23. `kubectl delete pv --all` ==> It will delete all PersistentVolumes, you should run it on your MiniKube cluster to learn it.
24. `kubectl get pvc -A` ==> Lists all the PersistentVolumeClaims in all namespaces.
25. `kubectl get roles` ==> 
26. `kubeadm join <master-ip>:6443 --token <token> --discovery-token-ca-cert-hash sha256:<hash>` ==> Kubeadm command to join the worker nodes with the master node in a K8s cluster.
27. `kubeadm token create --print-join-command` ==> Creates a new token if we forgot the older one.
