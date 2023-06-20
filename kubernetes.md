# hello-webapp

# kubernetes commands
## check version
kubectl version --output=yaml
kubectl version --output=json

## creating pods 
kubectl run nginx-webserver --image=nginx

## check pods and nodes
kubectl get pods
kubectl get nodes
## check detailed information on pods and nodes
kubectl describe pods
kubectl describe nodes

