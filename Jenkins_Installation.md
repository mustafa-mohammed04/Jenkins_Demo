# Jenkins_Demo
## Install jenkins Without docker or any container
``` bash
sudo apt-get update -y
```


## Install Java Runtime Environment 
``` bash
sudo apt install default-jre

```
## Add the Jenkins repository key to your system

``` bash
sudo wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update


```

## Install Jenkins 
``` bash 
sudo apt install jenkins -y
```
## Enable & Start Jenkins Service
``` bash
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
jenkins --version

```
