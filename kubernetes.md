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

## deleting pods
kubectl delete pod nginx-webserver

## check pods / nodes / replicasets
kubectl get pods
kubectl get nodes
kubectl get replicasets
## check detailed information on pods / nodes / replicasets
kubectl describe pods
kubectl describe nodes
kubectl describe replicaset
kubectl describe service

## replication controller creation
kubectl create -f file.yaml
## making changes
kubectl replace -f file.yaml
## deletion
kubectl delete replicaset <name_here>



## templates for pod creation


## networking 
## to get the exposed ports
kubectl get service

