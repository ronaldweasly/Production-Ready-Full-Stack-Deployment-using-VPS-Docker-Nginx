# 🚀 Production-Ready Full Stack Deployment using VPS, Docker & Nginx

---

## 📌 Overview

This project demonstrates deploying a full-stack web application on a cloud VPS using a containerized architecture. It showcases real-world DevOps practices including reverse proxy configuration, multi-service orchestration, and monitoring.

---

## 🔥 Live Demo

* Frontend: http://35.154.60.98
* API: http://35.154.60.98/api
* Grafana: http://35.154.60.98/grafana
* Prometheus: http://35.154.60.98/prometheus

---

## 🧱 Architecture

![Architecture](screenshots/architecture.png)

```text
User → Nginx → Frontend (Docker)
              → Backend API (Docker)
              → Grafana (Docker)
              → Prometheus (Docker)
```

---

## ⚙️ Tech Stack

* VPS (AWS EC2)
* Docker & Docker Compose
* Nginx (Reverse Proxy)
* Node.js (Backend API)
* HTML/CSS (Frontend)
* Prometheus (Monitoring)
* Grafana (Visualization)

---

## 🚀 Features

* Containerized frontend and backend services
* Reverse proxy routing using Nginx
* Multi-container orchestration using Docker Compose
* Centralized access via single entry point (port 80)
* Monitoring dashboards using Prometheus & Grafana
* Real-world debugging of:

  * Disk space issues
  * Port conflicts
  * Service failures

---

## 📂 Project Structure

```
/project
 ├── frontend/
 ├── backend/
 ├── screenshots/
 │    ├── architecture.png
 │    ├── frontend.png
 │    ├── api.png
 │    ├── docker.png
 │    ├── grafana.png
 │    └── prometheus.png
 ├── docker-compose.yml
 └── README.md
```

---

## 🔧 Setup Instructions

### 1. Clone Repository

```bash
git clone <your-repo-link>
cd project
```

### 2. Run Containers

```bash
docker compose up -d --build
```

### 3. Configure Nginx

```bash
nano /etc/nginx/sites-available/default
```

```nginx
server {
    listen 80;

    location / {
        proxy_pass http://localhost:3000;
    }

    location /api {
        proxy_pass http://localhost:5000;
    }

    location /grafana {
        proxy_pass http://localhost:3001;
    }

    location /prometheus {
        proxy_pass http://localhost:9090;
    }
}
```

```bash
systemctl restart nginx
```

---

## 🌐 Access

| Service    | URL                       |
| ---------- | ------------------------- |
| Frontend   | http://your-ip            |
| API        | http://your-ip/api        |
| Grafana    | http://your-ip/grafana    |
| Prometheus | http://your-ip/prometheus |

---

## 📸 Screenshots

### 🧱 Architecture
![Architecture](screenshots/ChatGPT%20Image%20May%204,%202026,%2012_22_53%20AM.png)

### 🖥️ Frontend
![Frontend](screenshots/Screenshot%202026-05-04%20001155.png)

### 🔌 API Response
![API](screenshots/Screenshot%202026-05-04%20001321.png)

### 🐳 Docker Containers
![Docker](screenshots/Screenshot%202026-05-04%20001241.png)

### 📊 Grafana Dashboard
![Grafana](screenshots/Screenshot%202026-05-04%20001400.png)

---

## 🧠 Key Engineering Decisions

* Used Docker to isolate services
* Used Nginx as a single entry point instead of exposing multiple ports
* Chose VPS for full infrastructure control
* Optimized system due to limited server resources

---

## ⚠️ Challenges Faced

* Disk space limitations on VPS
* Port conflicts during deployment
* Docker networking issues
* Service downtime debugging

---

## 🚀 Future Improvements

* Add HTTPS using Let's Encrypt
* Implement CI/CD using GitHub Actions
* Deploy with Kubernetes
* Add authentication & database

---

## 👨‍💻 Author

Himanshu
Engineering Student (AI & Data Science)
Focused on DevOps, Cloud & Scalable Systems
