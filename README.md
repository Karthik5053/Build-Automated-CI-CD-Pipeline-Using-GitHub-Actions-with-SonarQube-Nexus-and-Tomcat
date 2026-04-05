# Build-Automated-CICD-Pipeline-Using-GitHub-Actions-with-SonarQube-Nexus-and-Tomcat
---

## 🧠 Overview

This project implements an **Automated CI/CD Pipeline using GitHub Actions** for a Java web application.

It integrates:

- GitHub → Source Code Management  
- GitHub Actions → CI/CD Automation  
- Maven → Build Tool  
- SonarQube → Code Quality Analysis  
- Nexus → Artifact Repository  
- Tomcat → Deployment Server  

👉 The pipeline automates build, test, analysis, storage, and deployment.

---

## 🧱 Architecture Flow

Developer → GitHub → GitHub Actions → SonarQube → Nexus → Tomcat

---

## ⚙️ Step-by-Step Implementation

---

### 1️⃣ Create EC2 Instances

- Create EC2 instances for:
  - SonarQube
  - Nexus
  - Tomcat  
- (Optional: all can be installed in one server)  
- Name instances:
  - Sonarqube-server  
  - Nexus-server  
  - Tomcat-server  

---

### 2️⃣ Install SonarQube on EC2

- Update system:
  - `apt update -y`
- Install Docker:
  - `apt install docker.io -y`
- Start Docker  
- Run SonarQube container:

  docker run --name myc1 -d -p 9000:9000 sonarqube:latest

---

### 3️⃣ Install Nexus on EC2

- Install using Docker  
- Run Nexus container on EC2  

---

### 4️⃣ Install Tomcat on EC2

- Download Tomcat 9  
- Extract and configure  
- Run on port `8080`  

---

### 5️⃣ Login & Generate Token in SonarQube

- Open SonarQube using public IP  
- Login to SonarQube  
- Generate authentication token  

---

### 6️⃣ Login to Nexus

- Open Nexus using public IP  
- Login to Nexus  
- Copy repository URL  

---

### 7️⃣ Configure Tomcat

- Install Tomcat on EC2  
- Configure:
  - `tomcat-users.xml`  
- Add roles:
  - manager-gui  
  - manager-script  

---

### 8️⃣ Configure GitHub Repository

- Push source code to GitHub  
- Create workflow file:

  `.github/workflows/main.yaml`

- Add GitHub Secrets:
  - SONAR_HOST_URL  
  - SONAR_TOKEN  
  - NEXUS credentials  
  - TOMCAT credentials  

---

### 9️⃣ CI/CD Pipeline using GitHub Actions

- Pipeline steps:
  - Checkout code  
  - Setup Java (JDK 17)  
  - Run Maven:
    - validate  
    - compile  
    - test  
    - package  

- Upload WAR file as artifact  

- Deploy stages:
  - SonarQube → Code analysis  
  - Nexus → Store artifact  
  - Tomcat → Deploy WAR  

- Deployment uses:
  - Tomcat Manager API (via curl)

---

## 🚀 Final Output

- ✔ Code analyzed (SonarQube)  
- ✔ Artifact stored (Nexus)  
- ✔ Application deployed (Tomcat)  
- ✔ Fully automated CI/CD pipeline  

---
