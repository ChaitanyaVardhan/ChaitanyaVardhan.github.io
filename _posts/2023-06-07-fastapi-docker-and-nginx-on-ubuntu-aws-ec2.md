---
tags: [fastapi, web-frameworks, python]
---
Update the `apt` package index and install packages to allow apt to use repositories over https  
```
sudo apt-get update  
sudo apt-get install ca-certificates curl gnupg
```  

Add Docker's official gpg key  
```
$ sudo install -m 0755 -d /etc/apt/keyrings
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
$ sudo chmod a+r /etc/apt/keyrings/docker.gpg
```  

Use the below command to setup repository  
```
$ echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```  
### Install Docker Engine  
Update the apt index  
```
$ sudo apt-get update
```  
Install Docker Engine, Containerd and Docker Compose  
```
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
Verify the Docker Engine installation by running   
```
$ sudo docker run hello-world
```  
### Get basic fastapi repo  
```
$ https://github.com/ChaitanyaVardhan/fastapi-demo.git
```  

#### Setup NGINX  
```
$ sudo apt-get install nginx
```  

```
$ sudo vi /etc/nginx/sites-enabled/fastapi-demo
```  
Paste the below code and replace PUBLIC_IP with the ec2 public ip:  
```
server {
    listen 80;
    server_name <PUBLIC_IP>;
    location / {
        proxy_pass http://127.0.0.1:8000;
    }
}
```  
Restart NGINX and check its status:
```
$ sudo service nginx restart
$ sudo service nginx status
```  

### Start Docker container  
start the docker container in detached mode after cd into repo
```
$ sudo docker compose up -d

```  


