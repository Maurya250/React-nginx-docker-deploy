# React – Nginx – Docker Deployment

A production-ready deployment setup for serving a React application using Docker, Nginx, and Docker Compose. This project is built to help deploy React apps quickly on any Linux server, including AWS EC2.

---

## 🧰 Tech Stack
- React (Frontend)
- Nginx (Static Web Server)
- Docker
- Docker Compose

---

## 📂 Project Structure
.
├── Dockerfile
├── docker-compose.yml
├── nginx.conf
├── package.json
└── src/

React build output generates inside the build/ directory.

---

## 🚀 Local Development (Optional)
To test locally:
docker build -t react-nginx-app .
docker run -p 80:80 react-nginx-app

Open in browser:
http://localhost

---

## ☁️ Deployment on AWS EC2 (Production)

### 1️⃣ Install Docker & Docker-Compose
sudo apt update
sudo apt install docker.io docker-compose -y

### 2️⃣ Clone Repository
git clone git@github.com:Maurya250/React-nginx-docker-deploy.git
cd React-nginx-docker-deploy

### 3️⃣ Deploy the Application
sudo docker-compose up -d --build

### 4️⃣ Access Application
Open browser:
http://<EC2-PUBLIC-IP>

Make sure port 80 is open in EC2 Security Group firewall settings.

---

## 🛠 How It Works
- Docker builds React using Node inside a builder stage
- After build, output folder (build/) is copied into an Nginx container
- Nginx serves static files and also supports routing using:
  try_files $uri /index.html;

---

## 🔧 Useful Commands
Stop running containers:
docker-compose down

Force clean & rebuild:
docker system prune -f
docker-compose up -d --build

Check container logs:
docker logs <container-name>

---

## 👤 Author
Maintained by: Aniket Maurya

Repository:
git@github.com:Maurya250/React-nginx-docker-deploy.git

