## Installation Guide for Linux (Ubuntu 16.04)

*Resources: [Getting started with docker](https://www.youtube.com/watch?v=Vyp5_F42NGs)*

Description: Docker Engine is Linux Virtual Machine which allows containers to share the same resources. Docker is based on Linux container technology.
```docker --version```
```docker-compose --version```
**Docker-Compose** - a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration. To learn more about all the features of Compose, see the list of features.
[**Docker Hub**](https://hub.docker.com) contains docker images.


### 1. Uninstall old version(s)
Official method:
```
sudo apt-get remove docker docker-engine docker.io
```
Stackoverflow:
```
sudo apt-get purge -y docker-engine docker docker.io docker-ce  
sudo apt-get autoremove -y --purge docker-engine docker docker.io docker-ce  
```
Remove all images and containers
```
sudo rm -rf /var/lib/docker
sudo rm /etc/apparmor.d/docker
sudo groupdel docker
sudo rm -rf /var/run/docker.sock
```

### 2. Set up repository
```
sudo apt-get update

sudo apt-get install \ 
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
    
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo apt-key fingerprint 0EBFCD88

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

### 3. Install Docker CE
```
sudo apt-get update

sudo apt-get install docker-ce
```
Verify the installation:
```
sudo docker run hello-world
```

### 4. Installing images
##### 4.1. Pull an image and store locally (that makes it super easy to copy and install an environment on any suitable machine)
```docker pull <image-name>:<image-version>```
##### 4.2. Name a container properly
```docker run --name <my-container> <image-name>:<image-version>```
##### 4.3. Give parameters
Define port ```-p 80:80```
Use deamon to let the container run in background ```-d```

### 5. Issues with container parametrization 
Once a container is created with runtime settings, it cannot be changed. You have to recreate a new container with new settings. In this case, the data created in the container will be lost

