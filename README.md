# Apredendo Kubernets com o Kube.Dev

# conversao-temperatura


docker container ls -a

docker container rm iddocontainer

docker container rm -f iddocontainer

docker container run -it ubuntu /bin/bash

docker container run nginx

docker container run -d nginx

docker container run -d -p 8080:80 nginx

docker container run -d -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=mongouser -e MONGO_INITDB_ROOT_PASSWORD=mongopwd mongo

docker container inspect id

docker container exec -it d44cd28e1e64 /bin/bash

docker stop id

docker status id

docker start id

docker container logs 144d67d108ce

docker container logs -n 5 id

docker container logs -f id

docker container logs -t id 


#docker commit (não recomendado )
docker container run -it ubuntu /bin/bash 
apt-get update
apt-get install curl --yes
docker container ls -a
docker commit 0999ed848f3c ubuntu-curl-commit
docker image ls
docker container run -it ubuntu-curl-commit /bin/bash



#docketfile
FROM ubuntu
RUN apt-get update
RUN apt-get install curl --yes

docker image build -t ubuntu-curl-file .
docker image ls

#docketfile
FROM ubuntu
RUN apt-get update && RUN apt-get install curl --yes && RUN apt-get install vim --yes
docker image ls
docker image prune
docker image rm ubuntu 
docker image inspect id
docker image history id




**********************
**VSCODE**
FROM node
WORKDIR /app
COPY package*.json ./
RUN npm install 
COPY . .
EXPOSE 8080
CMD ["node", "server.js"]


docker image build -t conversao-temperatura . 
docker image ls
docker container run -d -p 8080:8080 conversao-temperatura 
docker container ls

docker image build -t souzajean/conversao-temperatura:v1 . 

.Dockerignore
node_module/

docker login
docker push souzajean/conversao-temperatura:v1 
docker tag souzajean/conversao-temperatura:v1 souzajean/conversao-temperatura:latest

docker container run -d -p 8080:8080 souzajean/conversao-temperatura:v1  
