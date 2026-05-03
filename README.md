# 🚀 Production-Ready Full Stack Deployment using VPS, Docker & Nginx

## 📌 Overview

This project demonstrates deploying a full-stack web application on a cloud VPS using a containerized architecture. It showcases real-world DevOps practices including reverse proxy configuration, multi-service orchestration, and system monitoring.

The system consists of:

* Frontend (static website)
* Backend (Node.js API)
* Reverse Proxy using Nginx
* Containerization using Docker
* Monitoring using Prometheus & Grafana

---

## 🧱 Architecture

```
User → Nginx → Frontend (Docker)
              → Backend API (Docker)
              → Monitoring (Grafana / Prometheus)
```

* Nginx routes:

  * `/` → frontend
  * `/api` → backend
  * `/grafana` → Grafana dashboard
  * `/prometheus` → Prometheus UI

---

## ⚙️ Tech Stack

* VPS (Cloud Server)
* Docker & Docker Compose
* Nginx
* Node.js (Backend)
* HTML/CSS (Frontend)
* Prometheus
* Grafana

---

## 🚀 Features

* Containerized frontend and backend services
* Reverse proxy routing using Nginx
* Multi-container orchestration using Docker Compose
* Centralized access via single entry point (port 80)
* Monitoring dashboards for system metrics
* Real-world debugging of:

  * Disk space issues
  * Port conflicts
  * Service failures

---

## 📂 Project Structure

```
/project
 ├── frontend/
 │   ├── index.html
 │   ├── style.css
 │   └── Dockerfile
 │
 ├── backend/
 │   ├── server.js
 │   ├── package.json
 │   └── Dockerfile
 │
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

---

### 2. Run Containers

```bash
docker compose up -d --build
```

---

### 3. Configure Nginx

Edit:

```bash
nano /etc/nginx/sites-available/default
```

Add:

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

Restart:

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

*Add these:*

* Running containers (`docker ps`)
* Frontend UI
* API response
* Grafana dashboard
* Prometheus UI

---

## 🧠 Key Learnings

* How to deploy applications on a VPS
* Reverse proxy configuration using Nginx
* Docker-based microservice architecture
* Debugging real-world deployment issues
* Resource optimization and system stability

---

## ⚠️ Challenges Faced

* Disk space limitations on VPS
* Port conflicts during deployment
* Networking between containers and host
* Service downtime and debugging

---

## 🚀 Future Improvements

* Add HTTPS using Let's Encrypt
* Implement CI/CD using GitHub Actions
* Deploy using Kubernetes for scalability
* Add authentication & database

---

## 👨‍💻 Author

Himanshu
Engineering Student (AI & Data Science)
Focused on DevOps, Cloud & Scalable Systems

---
