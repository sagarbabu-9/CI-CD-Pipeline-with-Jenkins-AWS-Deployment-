# CI/CD Pipeline with Jenkins & AWS Deployment

An end-to-end DevOps project demonstrating Continuous Integration and Continuous Deployment (CI/CD) using **Jenkins**, **Docker**, **GitHub Webhooks**, and **AWS EC2**. The pipeline automatically builds, tests, containerizes, and deploys a web application whenever code is pushed to the GitHub repository.

---

## 📌 Project Overview

This project automates the software delivery process by integrating GitHub with Jenkins. Every code push triggers a Jenkins pipeline that builds the application, creates a Docker image, and deploys the containerized application to an AWS EC2 instance running Nginx as a reverse proxy.

The objective is to eliminate manual deployment, ensure consistent environments, and accelerate application delivery.

---

## 🏗️ Architecture

```text
                Developer
                    │
             Push Code to GitHub
                    │
                    ▼
           GitHub Webhook Trigger
                    │
                    ▼
                Jenkins Server
                    │
        ┌───────────┴───────────┐
        │                       │
   Build Application      Build Docker Image
        │                       │
        └───────────┬───────────┘
                    ▼
            Deploy to AWS EC2
                    │
                    ▼
          Docker Container Running
                    │
                    ▼
          Nginx Reverse Proxy
                    │
                    ▼
                 End Users
```

---

## 🚀 Features

- Automated CI/CD pipeline using Jenkins
- GitHub Webhooks for automatic build triggers
- Docker-based application containerization
- Deployment to AWS EC2
- Nginx reverse proxy configuration
- Repeatable and reliable deployments
- Environment consistency across development and production
- Reduced manual deployment effort
- Faster software delivery

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| Jenkins | CI/CD Automation |
| Git & GitHub | Source Code Management |
| GitHub Webhooks | Automatic Pipeline Trigger |
| Docker | Application Containerization |
| AWS EC2 | Application Hosting |
| Nginx | Reverse Proxy |
| Linux (Ubuntu) | Deployment Server |
| Shell Scripting | Deployment Automation |

---

## 📂 Repository Structure

```text
DevOps-CI-CD-Pipeline-project/
│
├── app.py
├── requirements.txt
├── Dockerfile
├── Jenkinsfile
├── .github/
│   └── workflows/
├── scripts/
├── nginx/
└── README.md
```

---

## ⚙️ Pipeline Workflow

### Step 1 – Developer Pushes Code

Developers push application changes to the GitHub repository.

↓

### Step 2 – GitHub Webhook

GitHub automatically notifies Jenkins.

↓

### Step 3 – Jenkins Pipeline

Jenkins performs:

- Source Code Checkout
- Build
- Dependency Installation
- Docker Image Build
- Container Deployment

↓

### Step 4 – AWS EC2 Deployment

The Docker container is deployed on an AWS EC2 instance.

↓

### Step 5 – Application Access

Users access the application through Nginx.

---

## 🔄 CI/CD Workflow

```text
GitHub
   │
   ▼
Webhook
   │
   ▼
Jenkins
   │
   ├── Checkout Code
   ├── Build
   ├── Test (Optional)
   ├── Build Docker Image
   ├── Stop Old Container
   ├── Start New Container
   ▼
AWS EC2
   │
   ▼
Docker Container
   │
   ▼
Nginx
   │
   ▼
Users
```

---

## 📋 Prerequisites

Before running this project, ensure you have:

- Git
- Jenkins
- Docker
- AWS Account
- EC2 Instance
- GitHub Repository
- Nginx
- SSH Access to EC2

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/sagarbabu9/DevOps-CI-CD-Pipeline-project.git
cd DevOps-CI-CD-Pipeline-project
```

---

### 2. Configure Jenkins

- Install required plugins
- Create a Pipeline Job
- Connect GitHub repository
- Configure GitHub Webhook
- Add SSH credentials for EC2 deployment

---

### 3. Configure Docker

Build the Docker image:

```bash
docker build -t my-app .
```

Run the container:

```bash
docker run -d -p 80:80 my-app
```

---

### 4. Configure AWS EC2

- Launch an Ubuntu EC2 instance
- Install Docker
- Install Nginx
- Open ports:
  - 22 (SSH)
  - 80 (HTTP)
  - 443 (HTTPS)
  - 8080 (Jenkins, if required)

---

### 5. Configure Nginx

Set up Nginx as a reverse proxy to forward incoming traffic to the Docker container.

---

## 🔐 Security Best Practices

- SSH Key Authentication
- IAM Least Privilege
- Secure GitHub Webhooks
- Docker Image Isolation
- Firewall & Security Groups
- Nginx Reverse Proxy
- Secure Jenkins Credentials

---

## 📈 Results

- Automated end-to-end deployment
- Eliminated repetitive manual deployment tasks
- Consistent deployment environments using Docker
- Faster application delivery
- Improved deployment reliability
- Scalable deployment process

---

## 🎯 Learning Outcomes

This project helped me gain hands-on experience with:

- CI/CD Concepts
- Jenkins Pipeline
- GitHub Integration
- GitHub Webhooks
- Docker
- Container Deployment
- AWS EC2
- Nginx Reverse Proxy
- Linux Administration
- Deployment Automation
- DevOps Best Practices

---

## 🔮 Future Enhancements

- Kubernetes Deployment
- AWS ECS / EKS
- Terraform for Infrastructure as Code
- Ansible Automation
- SonarQube Integration
- Automated Unit Testing
- Prometheus Monitoring
- Grafana Dashboard
- Slack Notifications
- Blue-Green Deployment

---

## 👨‍💻 Author

**Sagar Babu**

DevOps & Cloud Enthusiast

---

## 📄 License

This project is created for learning, portfolio, and demonstration purposes.
