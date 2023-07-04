# Azure cli commans

az group list
az group create -l westeurope -n cli-group

az appservice plan create --resource-group cli-group --name azure-myplan --is-linux
az webapp create -g cli-group -n hello -p azure-myplan -r PYTHON:3.11 -b 


az webapp create-remote-connection -n webapp-hello -g cli-group

az webapp delete -n webapp-hello -g cli-group


# python3 commands

sudo dnf install python3*
sudo dnf install pip3*
sudo pip3 install psycopg2-binary (or) sudo pip3 install -r requirements.txt


# Docker commands
# install from official site 

## installing docker with security (docker runs nativey with limited capability from root user, so can further abilities to container)
docker run --cap-add SYS_ADMIN nginx
docker run --cap-drop KILL nginx
docker run --privileged nginx (with all rights)

docker run --user=1001 nginx

## creating network
sudo docker network create network-yuva
## creating containers with user-defined network
sudo docker run -it -p 85:80 --net=network-yuva --name enginex-server nginx

## creating PostgreSQL database container under bridge network
sudo docker run -d -e POSTGRES_USER=root -e POSTGRES_DB=rootdb -e POSTGRES_PASSWORD=root --net=network-yuva --name pg-yuva -p 5432:5432 postgres

# kubernetes commands
## check version
kubectl version --output=yaml
kubectl version --output=json
kubectl cluster-info

## creating pods 
kubectl run nginx-webserver --image=nginx -o yaml
kubectl create -f file.yaml

## editing created pods
kubectl edit pod nginx-webserver

## making changes to file
kubectl replace -f file.yaml

## deleting pods
kubectl delete pod nginx-webserver

## check pods / nodes / replica sets / namespaces 
kubectl get pods
kubectl get nodes
kubectl get replicasets
kubectl get deploymentsets
kubectl get services
kubectl get all
kubectl get ns
kubectl get pods --namespace=<typehere>
kubectl get configmaps
kubectl get configmaps --namespace=<typehere>

## check detailed information on pods / nodes / replicasets
kubectl describe pods
kubectl describe nodes
kubectl describe replicaset
kubectl describe service



## imperative commands
### check logs
kubectl logs <app_name> -n <namespace-here>
### config maps
kubectl create configmap webapp-config-map --from-literal=APP_COLOR=darkblue --from-literal=APP_OTHER=disregard
