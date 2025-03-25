# 🚀 ZSOFTLY Capstone Project Part Two: Automating Docker Image Deployment to Amazon ECR

## Technical Stack
- **Cloud**: AWS
- **CI/CD**: GitHub Actions
- **Containerization**: Docker
- **Image Repository**: Amazon ECR

## Objectives
- Automate Docker image builds and pushes to ECR on pull requests.
- Manage three environments: Dev, Staging, and Prod.
- Implement secure AWS authentication using GitHub Actions Secrets.

## CI/CD Flow
1. Developer creates a Pull Request.
2. GitHub Actions triggers and builds Docker images for all environments.
3. Docker images are tagged and pushed to their respective ECR repositories.

## Project Structure
- `.github/workflows/docker-ecr.yml`: GitHub Actions workflow file.
- `app/`: Application source code and Dockerfile.
- `README.md`: Project documentation.

## Environment-specific ECR Repositories
- `zsoftly-dev`
- `zsoftly-staging`
- `zsoftly-prod`

## Setup Instructions
1. Create the 3 ECR repos in AWS.
2. Add the following secrets to GitHub:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
   - `AWS_REGION`

3. Make a Pull Request to trigger the workflow.

## Author
CHEBM | DevOps Engineer Starter
