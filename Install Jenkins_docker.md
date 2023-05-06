# Jenkins_Demo

## Installation jenkins as docker container
``` bash
sudo apt-get update -y
sudo docker run -p 8080:8080 -p 50000:50000 -d \
 -v jenkins_home:/var/jenkins_home \
 -v /var/run/docker.sock:/var/run/docker.sock \
 -v $(which docker):/usr/bin/docker jenkins/jenkins:lts
```

## view your container is up and running
``` bash
docker ps
```

## to exec inside your container
``` bash
docker exec -it crazy_shockley bash            >> container-name  crazy_shockley
```

## to exec as root user inside your container
``` bash
docker exec -u 0 -it crazy_shockley bash
```
## to retrieve jenkins initation password 
``` bash
docker exec -it  crazy_shockley bash 
cat /var/jenkins_home/secrets/initialAdminPassword 
```

## Or Outside Container  to retrieve jenkins initation password 
``` bash
docker volume inspect jenkins_home
cd /var/lib/docker/volumes/jenkins_home/_data/secrets
ls
initialAdminPassword  jenkins.model.Jenkins.crumbSalt  master.key
cat initialAdminPassword
```

## #to download build tools manually from inside the container (nodejs)
``` bash
docker exec -u 0 -it container-name bash 
cat /etc/issue #to know which version of linux you are on 
apt update 
apt install curl 
curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh
ls
bash node source_setup.sh
sudo apt-get install -y nodejs
node -v 
npm -v 
```
