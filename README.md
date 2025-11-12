# React-Application DevOps Project

## 🚀 Project Overview
This project demonstrates a complete **DevOps pipeline** for a React web application, covering:

- Application deployment on AWS EC2
- Containerization using Docker and Docker Compose
- Continuous Integration & Deployment (CI/CD) automation with Jenkins
- Monitoring and alerting for application health
- Branch-based Docker image deployments for dev and production environments

The project ensures a **scalable, automated, and maintainable DevOps workflow** for front-end applications.

The application source code was referenced from:  
[devops-build](https://github.com/sriram-R-krishnan/devops-build.git)

---

## 🧩 Key Highlights

| Feature | Description |
|---------|-------------|
| **Application Deployment** | Hosted on AWS EC2 instance, accessible via port 800 |
| **Containerization** | Dockerfile for single-container deployment, managed via Docker Compose |
| **CI/CD Pipeline** | Jenkins automates build, push, and deployment processes |
| **Branch-Based Deployment** | `dev` branch → Docker image pushed to public repo; `main` branch → Docker image pushed to production repo |
| **Monitoring & Alerts** | Open-source monitoring setup integrated to track uptime and health |
| **Security** | AWS Security Groups restrict access to authorized IPs; DockerHub credentials securely managed via Jenkins |

---

## 🏗️ Architecture & Workflow

### 1. Application Deployment
- Deployed React application on **port 800** of an AWS EC2 instance.
- Configured Security Groups for:
  - Application access: Open for all users
  - Server login: Restricted to your public IP

### 2. Containerization
- Created **Dockerfile** for containerizing the application.
- Docker Compose manages multi-container setups (if needed for additional services).

### 3. Automation with Bash Scripts
- `build.sh` → Builds Docker image locally.
- `deploy.sh` → Deploys the image to the EC2 instance automatically.

### 4. CI/CD Pipeline (Jenkins)
- Configured Jenkins to:
  - Trigger builds automatically on `dev` and `main` branches.
  - Build, scan, and push Docker images to Docker Hub.
  - Deploy the application automatically to the server.
- Branch-specific DockerHub repositories:
  - `dev` branch → public repo
  - `main` branch → production repo

### 5. Monitoring & Alerts
- Integrated a monitoring system to track:
  - Application uptime
  - Resource utilization
- Configured alert notifications for any downtime or failures.

---

## 📊 Tools & Technologies

| Category | Tools & Services |
|----------|-----------------|
| Application | React.js, Node.js |
| Containerization | Docker, Docker Compose |
| CI/CD | Jenkins, Bash Scripts |
| Version Control | Git & GitHub |
| Hosting | AWS EC2, Security Groups |
| Monitoring | Open-source monitoring tools |
| Container Registry | Docker Hub |

---

## 🛠️ Step-by-Step Execution

1. Clone the source code repository:
   ```bash
   git clone https://github.com/sriram-R-krishnan/devops-build.git

2. Build Docker image:
   ./build.sh

3. Deploy Docker container:
   ./deploy.sh

4. Jenkins triggers automatic CI/CD pipelines on dev or main branches.
   
5. Monitor application health using the integrated monitoring system.

--- 

##📝 Activity Logs & Screenshots

All project steps, Jenkins builds, AWS EC2 setup, Docker Hub images, and monitoring dashboards are documented in the dev branch.
These screenshots provide a visual reference of the pipeline execution and the deployed application.

---

##🎯 Outcome

Fully automated CI/CD pipeline for a React application.
Branch-based deployment strategy for dev and production environments.
Containerized deployment with Docker and Docker Compose.
Integrated monitoring and alerting system to ensure application uptime.

---

##💡 Notes

Branches:
main → Contains production-ready configuration and deployment scripts
dev → Contains configuration files and activity logs
SonarQube code quality checks can be optionally configured as part of CI/CD.

---

## 👤 Contributors
**Danush Vithiyarth Jaiganesh** – DevOps Engineer 
