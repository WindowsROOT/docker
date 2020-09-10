######################## git clone #############################

git clone https://github.com/WindowsROOT/docker.git

cd docker

docker network create nginx-proxy 

fuser -n tcp -k 80

cd nginx-proxy/
docker-compose up -d

cd /home/ubuntu/docker/docker/web1/
nano docker-compose.yml
edit > wordpress > environment: > targat domain  
docker-compose up -d

----------config mysql -------------
docker exec -it {id} bash

mysql -u root -pPASSWORD
CREATE DATABASE wordpress2;
FLUSH PRIVILEGES;
exit
exit

cd /home/ubuntu/docker/docker/web2/
nano docker-compose.yml
edit > wordpress > environment: > targat domain  
docker-compose up -d






###############################################################
#add to git 
git init
git add README.md
git commit -m "first commit"
git branch -M master
git remote add origin https://github.com/WindowsROOT/docker.git
git push -u origin master


