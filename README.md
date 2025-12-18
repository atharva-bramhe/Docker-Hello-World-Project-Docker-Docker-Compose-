# Docker Hello World Project

## Overview
This project demonstrates how to containerize a simple web application using **Docker** and manage it using **Docker Compose**.  
It covers building a Docker image, pushing it to Docker Hub, and running the application with Docker Compose.

---

## Prerequisites
- Linux system (Amazon Linux / RHEL / CentOS)
- Docker installed
- Docker Compose v2 installed
- Git installed
- Docker Hub account


## 1. Install Docker

```bash
sudo yum update -y
sudo yum install docker -y
```

Start and enable Docker:

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

Verify installation:

```bash
docker --version
```

---

## 2. Install Docker Compose (v2)

```bash
sudo mkdir -p /usr/local/lib/docker/cli-plugins
sudo curl -SL https://github.com/docker/compose/releases/download/v2.27.0/docker-compose-linux-x86_64 \
-o /usr/local/lib/docker/cli-plugins/docker-compose
sudo chmod +x /usr/local/lib/docker/cli-plugins/docker-compose
```

Verify:

```bash
docker compose version
```

---

## 3. Install Git

```bash
sudo yum install git -y
```

(Optional) Configure Git:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

---

## 4. Clone the Project Repository

```bash
git clone https://github.com/atulkamble/docker-hello-world.git
cd docker-hello-world
```

---

## 5. Dockerfile

The `Dockerfile` is used to build the application image.

```bash
cat Dockerfile
```

---

## 6. Build Docker Image

Login to Docker Hub:

```bash
docker login
```

Build the image:

```bash
docker build -t <dockerhub-username>/docker-hello-world .
```

---

## 7. Push Image to Docker Hub

```bash
docker push <dockerhub-username>/docker-hello-world
```

---

## 8. Run Application Using Docker Compose

The `docker-compose.yml` file defines and runs the application services.

View the file:

```bash
cat docker-compose.yml
```

Start services:

```bash
docker compose up -d
```

Stop services:

```bash
docker compose down
```

---

## 9. Verify Running Containers

```bash
docker container ls
```

Access the application in a browser:

```text
http://<server-ip>:80
```

---


