# MariaNginx For NodeJs
Docker-compose file for Mariadb + Nginx \
MariaDB : lastest \
Nginx : 1.13 \
Create By lulu \
https://cafe.naver.com/soyeoncode
# Setup
```
 yum update
 yum install -y docker docker-compose docker-registry

 systemctl enable docker.service
 systemctl start docker.service

 git clone https://github.com/teddy258/MariaNginx.git docker
 cd docker
```
# Config files
```
 vim docker-compose.yml

MYSQL_DATABASE=<Your Database name>  #default : adonis
MYSQL_ROOT_PASSWORD=<Your Password>  #default : 1234

 vim nginx/default.conf
 
server_name <Your hostname>
proxy_pass http://127.0.0.1:<Your port>;

# Reload Nginx config
 docker container exec <ContainerID> nginx -s reload
```
# Start Dcoker
```
# Create container
 docker-compose up -d

# Create container with recreate
 docker-compose up -d --force-recreate

# Down all container
 docker-compose down
```
# Directory
```
# Files
Nginx conf : /nginx 
MariaDB cnf : /mariadb

# Data Directory
MariaDB data : /data
```
# Access inside Docker-Container 
```
# List of Container
 docker ps
# Get in to container
 docker exec -it <ContainerID> bash
```



