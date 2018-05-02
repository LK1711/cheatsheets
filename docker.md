## Installation Guide for Linux (Ubuntu 16.04)

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
