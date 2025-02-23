# MentoBridge

## Overview
This project consists of three repositories:
- **Frontend Repository:** `frontend-repo`
- **Backend Repository:** `backend-repo`
- **Infrastructure Repository:** `infra-repo`

Each repository follows a structured branching model to ensure efficient development, testing, and deployment.

## 🛠Tech Stack
- **Frontend:** React.js, Tailwind CSS
- **Backend:** Node.js, Express.js
- **Database:** PostgreSQL
- **Hosting:** AWS (EC2, RDS, S3, CloudFront)
- **Authentication:** JWT (JSON Web Token)
- **Deployment:** GitHub Actions & AWS CodeDeploy
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

### **2️⃣ Clone the Repositories**
```sh
git clone https://github.com/org-name/frontend-repo.git
cd frontend-repo
```
```sh
git clone https://github.com/org-name/backend-repo.git
cd backend-repo
```
```sh
git clone https://github.com/org-name/infra-repo.git
cd infra-repo
```

### **3️⃣ Backend Setup**
```sh
cd backend-repo
npm install
```
#### **Environment Variables (`.env`)**
> Instead of storing secrets in `.env`, use AWS Secrets Manager.

#### **Run the Backend**
```sh
npm run dev
```

### **4️⃣ Frontend Setup**
```sh
cd ../frontend-repo
npm install
```
#### **Environment Variables (`.env` in `frontend-repo/`)**
```plaintext
REACT_APP_API_URL=http://localhost:5000
```
#### **Run the Frontend**
```sh
npm start
```

---

## Project Structure
```
frontend-repo/             # React.js Frontend
│── src/
│   ├── components/      # Reusable UI components
│   ├── pages/           # Main pages
│   ├── hooks/           # Custom hooks
│── .github/workflows/   # GitHub Actions CI/CD
│── .gitignore           # Ignore unnecessary files

backend-repo/              # Node.js API
│── src/
│   ├── controllers/     # Business logic
│   ├── models/          # Database models
│   ├── routes/          # API endpoints
│   ├── middleware/      # Auth & security
│   ├── config/          # Configurations (DB, AWS, etc.)
│── .github/workflows/   # GitHub Actions CI/CD
│── .gitignore           # Ignore unnecessary files

infra-repo/                # AWS Infrastructure
│── terraform/           # Terraform files
│── scripts/             # Deployment scripts
│── .github/workflows/   # GitHub Actions for Infrastructure as Code
```

---

## API Endpoints
### **Versioned API (`/api/v1`)**
### **Authentication**
- `POST /api/v1/auth/register` → Register new user
- `POST /api/v1/auth/login` → Login & get JWT token

### **Users**
- `GET /api/v1/users/profile` → Get user profile
- `PUT /api/v1/users/profile` → Update user profile

---

## Database Migrations
- **Using Sequelize (ORM for PostgreSQL):**
```sh
npx sequelize-cli db:migrate
```
- **Revert Last Migration:**
```sh
npx sequelize-cli db:migrate:undo
```

---

## Contributing
Want to contribute? Follow these steps:
1. Fork this repo
2. Create a new branch (`git checkout -b feature-branch`)
3. Make your changes & commit (`git commit -m 'Added feature XYZ'`)
4. Push to your branch (`git push origin feature-branch`)
5. Open a **Pull Request**

---

## 📄 License
This project is licensed under the MIT License. See the `LICENSE` file for details.


