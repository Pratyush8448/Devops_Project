# 🚀 AWS CI/CD Pipeline Automation Using Terraform

This project demonstrates the implementation of a fully automated CI/CD pipeline on AWS using Terraform as Infrastructure as Code (IaC). The pipeline automates the process of building, testing, containerizing, and deploying a frontend application using various AWS DevOps services.

The project was designed with modular Terraform architecture to ensure scalability, maintainability, reusability, and production-grade infrastructure management.

---

# 📌 Project Objectives

The primary objectives of this project were:

- Automate infrastructure provisioning using Terraform
- Implement a complete CI/CD pipeline on AWS
- Integrate source control with GitHub
- Automate application build and deployment workflows
- Containerize the frontend application using Docker
- Push Docker images to Amazon ECR
- Deploy the application using AWS services
- Modularize Terraform code for maintainability
- Validate infrastructure using Terratest

---

# 🏗️ Architecture Overview

The CI/CD pipeline follows the workflow below:

```text
Developer Pushes Code to GitHub
                ↓
        AWS CodePipeline
                ↓
         AWS CodeBuild
                ↓
     Build Docker Image
                ↓
      Push Image to ECR
                ↓
      Deploy Application
                ↓
     ECS / EC2 Deployment
```

---

# ⚙️ Technologies Used

## Infrastructure as Code
- Terraform
- Terratest

## AWS Services
- AWS CodePipeline
- AWS CodeBuild
- AWS CodeDeploy
- Amazon ECS
- Amazon ECR
- Amazon S3
- IAM
- VPC
- Application Load Balancer (ALB)

## Frontend Technologies
- React.js
- Vite
- JavaScript
- NGINX

## DevOps Tools
- Docker
- GitHub
- Git
- AWS CLI

---

# 🧩 Terraform Module Creation

To improve scalability and maintainability, the infrastructure was modularized using Terraform modules.

Each AWS service was implemented as an independent module.

## Modules Created

- Application Load Balancer (ALB)
- AWS CodeBuild
- AWS CodePipeline
- AWS CodeDeploy
- Amazon ECS
- Amazon ECR
- IAM Roles and Policies
- Amazon S3 Buckets
- VPC

Each module contains:

```text
main.tf       → Resource definitions
variables.tf  → Input variables
outputs.tf    → Exported outputs
```

This modular structure enables:
- code reusability
- easier debugging
- better organization
- simplified scaling
- maintainable infrastructure

---

# 🔄 CI/CD Pipeline Setup

The AWS CodePipeline was provisioned entirely using Terraform.

## Pipeline Stages

### 1️⃣ Source Stage
- Integrated with GitHub repository
- Automatically triggers on code push events

### 2️⃣ Build Stage
- Configured using AWS CodeBuild
- Builds Docker images
- Executes buildspec.yml
- Pushes images to Amazon ECR

### 3️⃣ Deploy Stage
- Uses AWS CodeDeploy / ECS deployment
- Deploys updated application containers

---

# 🔐 IAM Roles & Policies

Custom IAM roles and policies were created using Terraform to provide secure permissions for:

- CodePipeline
- CodeBuild
- ECS
- CodeDeploy
- ECR
- S3

Least privilege access principles were followed while assigning permissions.

---

# 🪣 S3 Artifact Storage

Amazon S3 buckets were provisioned to:
- store pipeline artifacts
- manage deployment packages
- support CI/CD workflows

---

# 🧪 Infrastructure Testing Using Terratest

Terratest was implemented to validate the Terraform infrastructure.

## Test Objectives

- Verify successful resource creation
- Validate module outputs
- Ensure infrastructure reliability
- Detect configuration issues early

Terratest improved confidence in infrastructure deployment and automation.

---

# 💻 Frontend Application Development

A frontend application was developed as part of the deployment pipeline.

## Application Details

- Book Library Application
- Built using React + Vite + JavaScript
- Production-ready static frontend

---

# 🐳 Docker Containerization

The frontend application was containerized using Docker.

## Dockerfile
The `Dockerfile` was created to:
- build the React application
- create production Docker images
- optimize deployment

---

# 🌐 NGINX Configuration

A custom `nginx.conf` file was configured to:
- serve static frontend files
- handle routing efficiently
- optimize production serving

---

# ⚡ AWS CodeBuild Configuration

A `buildspec.yml` file was created for AWS CodeBuild.

## Responsibilities

- install dependencies
- build Docker image
- authenticate with ECR
- push Docker image to Amazon ECR

---

# 📦 Amazon ECR Integration

Docker images generated during the build stage were pushed to Amazon Elastic Container Registry (ECR).

This enabled:
- secure image storage
- scalable deployments
- container version management

---

# 🚀 Deployment Workflow

The deployment workflow operates as follows:

1. Developer pushes code to GitHub
2. AWS CodePipeline triggers automatically
3. CodeBuild builds the application
4. Docker image is generated
5. Image is pushed to ECR
6. Deployment service deploys updated application
7. Application becomes available through ALB

---

# 🧠 Key Learning Outcomes

Through this project, the following concepts were implemented and understood:

- Infrastructure as Code (IaC)
- CI/CD pipeline automation
- Terraform modularization
- AWS DevOps services integration
- Docker containerization
- ECS deployments
- IAM security configuration
- Automated infrastructure testing
- Cloud-native deployment workflows

---

# 📈 Future Enhancements

Potential future improvements include:

- Kubernetes (EKS) integration
- Monitoring using CloudWatch
- Logging using ELK Stack
- Auto-scaling policies
- Blue-Green deployments
- HTTPS with ACM
- Multi-environment deployment setup
- GitHub Actions integration

---

# 🛠️ Installation & Setup

## 1️⃣ Clone Repository

```bash
git clone <repository-url>
```

---

## 2️⃣ Navigate to Project Directory

```bash
cd project-root
```

---

## 3️⃣ Initialize Terraform

```bash
terraform init
```

---

## 4️⃣ Validate Terraform Configuration

```bash
terraform validate
```

---

## 5️⃣ Preview Infrastructure Changes

```bash
terraform plan
```

---

## 6️⃣ Apply Infrastructure

```bash
terraform apply
```

---

# 🧪 Running Terratest

Navigate to the test directory and execute:

```bash
go test -v
```

---

# 📡 Pipeline Verification

After deployment:

- Push changes to GitHub
- Verify CodePipeline execution
- Check CodeBuild logs
- Confirm Docker image in ECR
- Validate successful deployment

---

# 📜 Conclusion

This project successfully implemented a complete end-to-end AWS DevOps CI/CD pipeline using Terraform.

The infrastructure was modularized for scalability and tested using Terratest to ensure reliability. The pipeline automated the complete workflow from source code integration to deployment, demonstrating practical implementation of modern DevOps and cloud engineering practices.

---

# 👨‍💻 Author

## Pratyush Nishank

- GitHub: https://github.com/Pratyush8448
- Portfolio: https://pratyush-nishank-portfolio.vercel.app

---

# ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.
