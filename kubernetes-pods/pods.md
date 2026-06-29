## Nginx
kubectl run nginx-pod --image=nginx --port=80

kubectl port-forward nginx-pod 8080:80

## MySQL
kubectl run mysql-pod --image=mysql:8.0 --env="MYSQL_ROOT_PASSWORD=my-secret"

## Python
kubectl run python-interactive --rm -i --tty --image=python:3.11 -- python
