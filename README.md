######################## git clone #############################

git clone https://github.com/WindowsROOT/docker.git

cd docker

docker network create nginx-proxy 
fuser -n tcp -k 80

#################Create Container Nginx#####################

cd nginx-proxy/
docker-compose up -d

#################Create Container DB1 & wordpress1 #################

cd /home/ubuntu/docker/docker/web1/
nano docker-compose.yml
edit > wordpress > environment: > targat domain  
docker-compose up -d

#################config mysql#################

docker exec -it {id} bash
mysql -u root -pPASSWORD
CREATE DATABASE wordpress2;
FLUSH PRIVILEGES;
exit
exit

#################Create Container wordpress1 #################

cd /home/ubuntu/docker/docker/web2/
nano docker-compose.yml
edit > wordpress > environment: > targat domain  
docker-compose up -d

################# SSL and domain #################
cloudflare.com 
ssl > Flexible 
DNS >add record A www.wp1.com > SAVE
DNS >add record A www.wp2.com > SAVE





##################  git ##################

git init
git add README.md
git commit -m "first commit"
git branch -M master
git remote add origin https://github.com/WindowsROOT/docker.git
git push -u origin master


