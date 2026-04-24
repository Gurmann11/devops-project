# CI/CD Pipeline using Jenkins & Docker

This project demonstrates an end-to-end CI/CD pipeline where code pushed to GitHub is automatically built and deployed using Jenkins and Docker.

It showcases automation of software delivery with minimal manual intervention.    

## ❗ Problem Statement

Manual deployment is time-consuming and error-prone. This project solves that by automating the build and deployment process using CI/CD practices.


---

## ⚙️ Tech Stack
- Jenkins
- Docker
- GitHub
- Linux

---

## 🏗️ Architecture

1. Developer pushes code to GitHub  
2. Jenkins detects changes and triggers the pipeline  
3. Application is built and Docker image is created  
4. Trivy scans the Docker image for vulnerabilities  
5. If no critical issues are found, the container is deployed  

---
## ▶️ How to Run

1. Clone the repository  
   git clone https://github.com/Gurmann11/ci-cd-pipeline-jenkins-docker.git

2. Navigate to project directory  
   cd ci-cd-pipeline-jenkins-docker

3. Build Docker image  
   docker build -t devops-app .

4. Run Docker container  
   docker run -d -p 5000:5000 devops-app

5. Access the application  
   Open http://localhost:5000 in your browser

## 📸 Screenshots

### Jenkins Pipeline
![Jenkins Pipeline](pipeline.png.png)

### Build Logs (Console Output)
![Build Logs](build-logs.png.png)

### Docker Container Running
![Docker Container](docker-container.png.png)


---

## 🚀 Outcome
- Automated build and deployment process  
- Reduced manual errors  
- Improved consistency across environments  

---

## 📂 Project Structure

- Jenkinsfile → Defines the CI/CD pipeline stages and trivy
- Dockerfile → Builds the application container  
- app/ → Contains application source code  
- README.md → Project documentation  
