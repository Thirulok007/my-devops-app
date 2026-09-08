
````markdown
Application Deployment using Docker, Terraform, AWS, DockerHub, Jenkins and Kubernetes

 Objective

Deploy the given application to a production-ready state using Docker, Terraform, AWS, DockerHub, Jenkins, Kubernetes and CI/CD.

---

 Application

 Repository

```text
https://github.com/Vennilavanguvi/Trend.git
````

Clone Repository

```bash
git clone https://github.com/Vennilavanguvi/Trend.git
cd Trend
```

Run Application

```bash
npm install
npm start
```

Application runs on:

```text
http://localhost:3000
```

---
 Tech Stack

| Category               | Tools                    |
| ---------------------- | ------------------------ |
| CI/CD                  | Jenkins                  |
| Infrastructure as Code | Terraform                |
| Containerization       | Docker                   |
| Orchestration          | Kubernetes (Amazon EKS)  |
| Cloud Provider         | AWS (EKS, ELB, VPC, EC2) |
| Application            | Node.js                  |

---

Architecture

GitHub → Jenkins → Docker → DockerHub → AWS EKS → Kubernetes → LoadBalancer → Application

---

Project Structure

```text
my-devops-app/
├── Dockerfile              # Container image definition
├── deployment.yaml         # Kubernetes Deployment manifest
├── service.yaml            # Kubernetes Service (LoadBalancer)
├── server.js               # Application source
├── package.json            # Node.js dependencies
└── screenshots/            # Project evidence
```

---

Version Control
 Initialize Git

```bash
git init
```

### Add Files

```bash
git add .
```

### Commit Changes

```bash
git commit -m "Initial commit"
```
Add Remote Repository

```bash
git remote add origin <GITHUB_REPOSITORY_URL>
```

Push Code

```bash
git branch -M main
git push -u origin main
```

The complete application code was pushed to GitHub.

Git Ignore Files

```text
.gitignore
.dockerignore
```

---

Docker

Create Dockerfile

A Dockerfile was created to containerize the application.

Build Docker Image

```bash
docker build -t my-devops-app .
```

Check Docker Image

```bash
docker images
```

Run Docker Container

```bash
docker run -d -p 3000:3000 --name my-devops-app my-devops-app
```

Check Container

```bash
docker ps
```

---

DockerHub

 Login to DockerHub

```bash
docker login
```

 Tag Docker Image

```bash
docker tag my-devops-app <DOCKERHUB_USERNAME>/my-devops-app
```

Push Docker Image

```bash
docker push <DOCKERHUB_USERNAME>/my-devops-app
```

The Docker image was pushed to DockerHub for deployment.

---

Terraform

Terraform is used to provision the required AWS infrastructure.

Infrastructure

* VPC
* IAM
* EC2
* Jenkins
* EKS

Initialize Terraform

```bash
terraform init
```

Validate Terraform

```bash
terraform validate
```

 Create Plan

```bash
terraform plan
```

Provision Infrastructure

```bash
terraform apply
```

---
 AWS EC2
An AWS EC2 instance was configured for Jenkins and DevOps operations.

---

Jenkins

Jenkins was installed and configured on the AWS EC2 instance.

 Required Plugins

* Git
* Docker
* Kubernetes
* Pipeline

Jenkins is used to automate the build, Docker image creation, DockerHub push and Kubernetes deployment.

---

 GitHub Webhook

GitHub and Jenkins were integrated using a GitHub webhook.

```text
GitHub Commit
      ↓
GitHub Webhook
      ↓
Jenkins Pipeline
```

The webhook automatically triggers the Jenkins pipeline when a new commit is pushed.

---

 CI/CD Pipeline

A declarative Jenkins pipeline was created using `Jenkinsfile`.

Pipeline Stages

```text
Checkout
   ↓
Build
   ↓
Docker Build
   ↓
DockerHub Push
   ↓
Kubernetes Deploy
```

---

 Kubernetes – AWS EKS

The application is deployed using Kubernetes on AWS EKS.

 Configure kubectl

```bash
aws eks update-kubeconfig --region <REGION> --name <CLUSTER_NAME>
```

Check Kubernetes Nodes

```bash
kubectl get nodes
```

---

Kubernetes Deployment

The application is deployed using `deployment.yaml`.

 Apply Deployment

```bash
kubectl apply -f deployment.yaml
```

Check Deployment

```bash
kubectl get deployment
```
 Check Pods

```bash
kubectl get pods
```

---

Kubernetes Service

The application is exposed using a Kubernetes LoadBalancer service.

 Apply Service

```bash
kubectl apply -f service.yaml
```

Check Service

```bash
kubectl get svc
```

---
 How It Works

1. **Provision** — Terraform spins up the VPC, EC2 (Jenkins server), IAM roles, and EKS cluster on AWS.
2. **Build** — Jenkins pipeline triggers on code push and builds a Docker image of the application.
3. **Push** — Docker image is pushed to DockerHub.
4. **Deploy** — Kubernetes manifests (`deployment.yaml`, `service.yaml`) deploy the application to the EKS cluster.
5. **Expose** — A Kubernetes `LoadBalancer` service provisions an AWS ELB and exposes the application publicly.

---

Monitoring

A monitoring system can be configured to check the health of the cluster and application.

The monitoring system can be used to monitor:

* CPU Usage
* Memory Usage
* Node Health
* Pod Health
* Application Availability

---

 Result

The application is deployed using Docker, Jenkins CI/CD and Kubernetes on AWS.

The application is accessible through the AWS Load Balancer:

```text
Hello from my DevOps App! CI/CD pipeline working
```

---

 Key Learnings

* Provisioning cloud infrastructure declaratively with Terraform
* Building automated CI/CD pipelines with Jenkins
* Containerizing applications with Docker
* Deploying and exposing services on Kubernetes (EKS)
* Managing Docker images using DockerHub
* Integrating GitHub with Jenkins using webhooks
* Debugging real-world AWS networking, Load Balancer, security groups and IAM roles

---

 Screenshot Documentation

The `screenshots/` folder contains the project implementation evidence, including:

* Application setup
* GitHub and Git commands
* Docker build and container
* DockerHub image
* Terraform infrastructure
* AWS EC2
* Jenkins installation and configuration
* Jenkins CI/CD pipeline
* Kubernetes EKS deployment
* LoadBalancer
* Final application output

```
