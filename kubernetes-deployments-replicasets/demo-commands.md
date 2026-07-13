## Replica Demo Commands

``kubectl apply -f replicaset-basic.yaml
kubectl get rs
kubectl get pods -l app=nginx --show-labels
kubectl describe rs nginx-rs``

## Self healing Demo Commands

``kubectl delete pod -l app=nginx --field-selector=status.phase=Running -o name | head -1 | xargs kubectl delete
kubectl get pods -l app=nginx -w``

## Deployment Demo Commands

``kubectl apply -f deployment-basic.yaml
kubectl get deploy,rs,pods -l app=nginx
kubectl describe deploy nginx-deployment``

## Rolling an NGINX update live

``kubectl apply -f dep-rolling-update.yaml
kubectl rollout status deployment/web-app``

## Trigger update by changing the image
``kubectl set image deployment/web-app web-app=nginx:1.25
kubectl rollout status deployment/web-app
kubectl get rs -l app=web-app -w``

## Rollback Demo
``kubectl rollout history deployment/web-app
kubectl rollout undo deployment/web-app
kubectl rollout undo deployment/web-app --to-revision=1
kubectl rollout status deployment/web-app``

## Manual Scaling
``kubectl scale deployment/web-app --replicas=8
kubectl get pods -l app=web-app``

## Port Forward

``kubectl port-forward deployment/api-deployment 8080:5678
curl localhost:8080``
