\# My DevOps App



A complete CI/CD pipeline project demonstrating automated build, infrastructure provisioning, and deployment using Jenkins, Terraform, Docker, and AWS EKS.



\## 🏗️ Architecture





\## 🛠️ Tech Stack



\- \*\*CI/CD:\*\* Jenkins

\- \*\*Infrastructure as Code:\*\* Terraform

\- \*\*Containerization:\*\* Docker

\- \*\*Orchestration:\*\* Kubernetes (Amazon EKS)

\- \*\*Cloud Provider:\*\* AWS (EKS, ELB, VPC)

\- \*\*App:\*\* Node.js



\## 📁 Project Structure



\- `Dockerfile` — Container image definition

\- `deployment.yaml` — Kubernetes Deployment manifest

\- `service.yaml` — Kubernetes Service (LoadBalancer) manifest

\- `server.js` — Application code

\- `package.json` — Node.js dependencies



\## 🚀 How It Works



1\. Jenkins pipeline triggers on code push

2\. Docker image is built from the app source

3\. Terraform provisions the EKS cluster and AWS infrastructure

4\. Kubernetes deployment applies `deployment.yaml` and `service.yaml`

5\. AWS Load Balancer exposes the app publicly



\## ✅ Result



App successfully deployed and accessible via AWS Load Balancer:





\## 📸 Screenshots



\### App Running

!\[App Running](screenshots/app-running.png)



\### Jenkins Setup

!\[Jenkins Setup](screenshots/jenkins-setup.png)



\### Docker Build \& Run

!\[Docker Build](screenshots/docker-build-run.png)



\### Terraform Provisioning

!\[Terraform Init](screenshots/terraform-init.png)



\### GitHub Push

!\[GitHub Push](screenshots/github-push.png)



\## 📌 Key Learnings



\- Setting up EKS clusters with Terraform

\- Writing Jenkins pipelines for automated CI/CD

\- Kubernetes Deployment and Service configuration

\- Exposing apps via AWS Load Balancer (ELB)

