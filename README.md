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

 Allow port : 3000, 3333
```
# Config files
```
# vim docker-compose.yml
MYSQL_DATABASE=<Your Database name>  #default : adonis
MYSQL_ROOT_PASSWORD=<Your Password>  #default : 1234

# nginx/default.conf
server_name <Your hostname>
proxy_pass http://172.17.0.1:<Your port>;

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

# CentOS Firewall
```
#Allow port
firewall-cmd --permanent --zone=public --add-port=80/tcp

#Disallow port
firewall-cmd --permanent --zone=public --remove-port=80/tcp

#Allow Service
firewall-cmd --permanent --zone=public --add-service=http,https

#Disallow Service
firewall-cmd --permanent --zone=public --remove-service=http,https

#Reload firewall
firewall-cmd --reload
```


