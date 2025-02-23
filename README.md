# MentoBridge

## Overview
This project consists of three repositories:
- **Frontend Repository:** `frontend-repo`
- **Backend Repository:** `backend-repo`
- **Infrastructure Repository:** `infra-repo`

Each repository follows a structured branching model to ensure efficient development, testing, and deployment.

## Tech Stack
- **Frontend:** React.js, Tailwind CSS
- **Backend:** Node.js, Express.js
- **Database:** PostgreSQL
- **Hosting:** AWS (EC2, RDS, S3)
- **Authentication:** JWT (JSON Web Token)
- **Deployment:** GitHub Actions 
- **Secrets Management:** AWS Secrets Manager
- **Infrastructure as Code (IaC):** Terraform

---

## Repository and Branch Structure

### **1️⃣ Frontend Repository (`frontend-repo`):**
- `master`: The stable production branch.
- `staging`: The branch used for testing before merging into `master`.
- `dev`: The integration branch for new features before merging into `staging`.
- `feature/<feature-name>`: Used for developing new features, branched from `dev`.
- `hotfix/<hotfix-name>`: Used for critical bug fixes in production, branched from `master`.

### **2️⃣ Backend Repository (`backend-repo`):**
- `master`: The stable production branch.
- `staging`: The branch used for testing before merging into `master`.
- `dev`: The integration branch for new backend features and fixes.
- `feature/<feature-name>`: Used for developing new backend features, branched from `dev`.
- `hotfix/<hotfix-name>`: Used for urgent bug fixes in production, branched from `master`.

### **3️⃣ Infrastructure Repository (`infra-repo`):**
- `master`: The stable infrastructure as code (IaC) branch for production.
- `dev`: The integration branch for infrastructure updates and changes.
- `feature/<feature-name>`: Used for infrastructure improvements or new configurations, branched from `dev`.
- `hotfix/<hotfix-name>`: Used for urgent fixes to infrastructure.

## Workflow
1. **Feature Development**: Developers create `feature/<feature-name>` branches from `dev`, work on changes, and create pull requests (PRs) back to `dev`.
2. **Testing and Review**: Changes in `dev` are tested in `staging` (for frontend, backend, and infrastructure), and once stable, merged into `master`.
3. **Hotfixes**: If a critical issue is found in production, a `hotfix/<hotfix-name>` branch is created from `master`, fixed, and merged back into both `master` and `staging` (if applicable).
4. **Deployment**: The `master` branch is used for production deployments, while `staging` (for frontend, backend, and infrastructure) is used for pre-production environments and `dev` for ongoing development.

## Naming Conventions
- **Features:** `feature/authentication-api`
- **Hotfixes:** `hotfix/critical-bug-fix`
- **Environment Branches:** `dev`, `staging`, `master`

---

## Getting Started

### **1️⃣ Prerequisites**
Ensure you have the following installed:
- [Node.js](https://nodejs.org/) (v16+ recommended)
- [PostgreSQL](https://www.postgresql.org/)
- AWS CLI (if deploying to AWS)
- Terraform CLI (if managing infrastructure)

### Please see repo specific README


