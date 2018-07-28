# Deployment File
Kubectl create -f deploymentexample.yml --record

kubectl set image deployment/nginx-deployment nginx=nginx:1.9.1

kubectl edit deployment/nginx-deployment

# Check Rollout Status
kubectl rollout status deployment/nginx-deployment

kubectl rollout undo deployment/nginx-deployment

kubectl rollout undo deployment/nginx-deployment --to-revision=2

kubectl rollout pause deployment/nginx-deployment

kubectl rollout resume deploy/nginx-deployment

