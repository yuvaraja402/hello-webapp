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
