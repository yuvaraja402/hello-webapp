# kubernetes commands
## check version
kubectl version --output=yaml
kubectl version --output=json

## creating pods 
kubectl run nginx-webserver --image=nginx -o yaml
kubectl create -f file.yaml

## editing created pods
kubectl edit pod nginx-webserver

## deleting pods
kubectl delete pod nginx-webserver

## check pods / nodes / replicasets
kubectl get pods
kubectl get nodes
kubectl get replicasets
## check detailed information on pods / nodes / replicasets
kubectl describe pods
kubectl describe nodes

## replication controller creation
kubectl create -f file.yaml
## making changes
kubectl replace -f file.yaml
## deletion
kubectl delete replicaset <name_here>



## templates for pod creation
