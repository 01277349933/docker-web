# Task 4: Web Server using Docker — CodeAlpha DevOps Internship

## 📌 Overview
This project deploys a static web server inside a Docker container using **Nginx Alpine**.
It demonstrates Docker containerization basics, container lifecycle management, and best practices.

## 🛠️ Technologies Used
- Docker
- Nginx (Alpine)
- HTML/CSS

## 📁 Project Structure
```
task4-docker-web/
├── Dockerfile        # Container build instructions
├── index.html        # Web page served by Nginx
└── README.md         # This file
```

## 🚀 How to Run

### 1. Build the Docker image
```bash
docker build -t docker-web .
```

### 2. Run the container
```bash
docker run -d -p 8080:80 --name web docker-web
```

### 3. Visit in browser
```
http://localhost:8080
```

## 🔍 Container Lifecycle Commands

| Command | Description |
|---|---|
| `docker ps` | List running containers |
| `docker logs web` | View container logs |
| `docker inspect web` | Inspect container details |
| `docker stop web` | Stop the container |
| `docker start web` | Start a stopped container |
| `docker rm web` | Remove the container |
| `docker rmi docker-web` | Remove the image |

## ✅ Health Check
The Dockerfile includes a built-in HEALTHCHECK that pings the server every 30 seconds to ensure the container is running correctly.

```bash
# Check health status
docker inspect --format='{{.State.Health.Status}}' web
```

## 🧹 Cleanup
```bash
docker stop web && docker rm web && docker rmi docker-web
```
