# 🚀 ZSOFTLY Capstone Project Part Two: Automating Docker Image Deployment to Amazon ECR

## 📦 Technical Stack
- **Cloud**: AWS ☁️
- **CI/CD**: GitHub Actions 🛠️
- **Containerization**: Docker 🐳
- **Image Repository**: Amazon ECR 📦
- **Source Control**: GitHub (public repository)

---

## 🎯 Objectives

### ✅ Create ECR Repository
Set up three private repositories in Amazon ECR:
- `zsoftly-dev`
- `zsoftly-staging`
- `zsoftly-prod`

### ✅ Set Up GitHub Actions Workflow
Implemented GitHub Actions using a matrix strategy to:
- Build Docker images
- Tag by environment (Dev, Staging, Prod)
- Push to corresponding ECR repositories on every pull request to `main`

### ✅ Configure AWS Credentials
Used GitHub Secrets to securely provide:
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION`

### ✅ Log into Amazon ECR
Used `aws-actions/amazon-ecr-login@v2` GitHub Action to authenticate and push to ECR.

### ✅ Build, Tag, and Push Docker Image
Docker images are built from `/app`, tagged according to the environment, and pushed to ECR:
```
<aws_account>.dkr.ecr.<region>.amazonaws.com/zsoftly-{dev|staging|prod}
```

---

## 🚀 How It Works

1. Developer pushes a change to a feature branch.
2. A Pull Request to `main` triggers GitHub Actions.
3. GitHub Actions:
   - Logs in to AWS
   - Builds Docker images
   - Tags them as `dev`, `staging`, and `prod`
   - Pushes them to their respective ECR repos

---

## 💡 Reflection Questions

### 1️⃣ How did you configure the CI/CD pipeline for multiple environments?
I used GitHub Actions with a **matrix strategy** to dynamically create jobs for `dev`, `staging`, and `prod`. Secrets and credentials were managed securely via GitHub Secrets. The biggest challenge was handling **ECR push errors** due to missing repos, which I resolved by pre-creating all 3 in the AWS Console.

### 2️⃣ How did managing 3 environments affect your approach to security and resource management?
It encouraged **clear separation of environments**, using tagged Docker images to avoid conflicts. It also made me think more about IAM permissions and isolation for future scaling into separate ECS services or VPCs.

### 3️⃣ What did you learn about cloud infrastructure and automation?
I learned:
- How to connect GitHub Actions securely with AWS
- Real-world Docker automation workflows
- ECR management and troubleshooting
- How to build reliable, repeatable pipelines for multi-environment deployments

---

## 📂 Repository Info

GitHub Repo: [Zsoftly-Capstone-Part2](https://github.com/CHEBLAISEM/Zsoftly-Capstone-Part2)

---

## 👨‍💻 Author
**CHEBM** – DevOps Engineer Starter  
This project was built as part of the ZSOFTLY Capstone Series to demonstrate real-world CI/CD and container deployment automation.

