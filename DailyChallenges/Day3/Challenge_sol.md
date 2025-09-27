# ✅ `challenge_solution.md` 

# Season-1: Day 3: Multi-Service Reverse Proxy with Nginx
**Name:** Manjunath K  
**Date:** 27 September 2025  

---

## ✅ Task 1 – Install all dependency packages in virtual machine ( Killer coda)

### Commands used:
```Bash
sudo apt update && sudo apt install -y docker.io docker-compose nginx apache2-utils openssl
sudo systemctl start docker
```
---

## ✅ Task 2 – Run Grafana & Jenkins via Docker

### Commands used:
```Bash
docker-compose.yml:
version: '3'
services:
  grafana:
    image: grafana/grafana:latest
    container_name: grafana
    ports:
      - "3000:3000"
  
  jenkins:
    image: jenkins/jenkins:lts
    container_name: jenkins
    user: root
    ports:
      - "8080:8080"
    volumes:
      - jenkins_home:/var/jenkins_home

volumes:
  jenkins_home:
#command to run services
docker-compose up -d

```

### Result:
Created docker-compose file to run the services ( jenkins & grafana)

---

## ✅ Task 3 – Install & Configure Nginx & Create self-signed SSL cert:

### Commands used:
```Bash
sudo apt install -y nginx
sudo mkdir -p /etc/nginx/ssl
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout /etc/nginx/ssl/selfsigned.key \
  -out /etc/nginx/ssl/selfsigned.crt \
  -subj "/CN=localhost"

```


### Result:
Installed nginx and created SSL cert for https access

---

## ✅ Task 4 – Configure Nginx Reverse Proxy

### Commands used:
```Bash
sudo nano /etc/nginx/sites-available/reverse-proxy.conf

reverse-proxy.conf:

server {
    listen 80;
    server_name grafana.local jenkins.local;

    return 301 https://$host$request_uri;
}

server {
    listen 443 ssl;
    server_name grafana.local;

    ssl_certificate /etc/nginx/ssl/selfsigned.crt;
    ssl_certificate_key /etc/nginx/ssl/selfsigned.key;

    location / {
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}

server {
    listen 443 ssl;
    server_name jenkins.local;

    ssl_certificate /etc/nginx/ssl/selfsigned.crt;
    ssl_certificate_key /etc/nginx/ssl/selfsigned.key;

    location / {
        proxy_pass http://localhost:8080;
        proxy_set_header Host $host;     # $host= grafana.local / jenkins.local
        proxy_set_header X-Real-IP $remote_addr;    #remote_addr is your laptop IP
    }
}

```

### Result:
Create config file to access jenkins & grafana with https

---

## ✅ Task 5 – Enable config

### Commands used:
```bash
sudo ln -s /etc/nginx/sites-available/reverse-proxy.conf /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl restart nginx
echo -e "IPofVM grafana.local\nIPofVM jenkins.local\n127.1.0.0 grafana.local\n127.1.0.0 jenkins.local " | sudo tee -a /etc/hosts


```

### Result:
Symlink nginx config to access from browser

---
## ✅ Task 5 – Access from browser
```bash
https://grafana.local
https://jenkins.local

```

## ✅ Submission Checklist

- ✅ Completed all tasks with commands and explanations
- ✅ Inserted screenshots under each command block
- ✅ Pushed code to GitHub
- ✅ Shared on LinkedIn with hashtags: `#getfitwithsagar #DevOpsForAll`

---