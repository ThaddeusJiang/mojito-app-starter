# Mojito Admin Starter

> 此项目主要为了演示如何自动化 Fullstack project 的 Infrastructure。

- [Mojito Admin Starter](#mojito-admin-starter)
  - [Involved content](#involved-content)
  - [Step1: Create Azure Cosmos DB and Function App](#step1-create-azure-cosmos-db-and-function-app)
  - [Step2: Deploy Web App to Vercel and deploy to Azure](#step2-deploy-web-app-to-vercel-and-deploy-to-azure)
  - [File Structure](#file-structure)

## Involved content

1. Next.js
2. Azure Functions
3. Terraform
4. GitHub Actions

## Step1: Create Azure Cosmos DB and Function App

1. setup `preview` environment, see [./infra/preview/main.tf](./infra/preview/main.tf)

```
cd infra/preview
terraform init
terraform plan -out=preview
terraform apply "preview"
```

2. setup `prod` environment with the same way

## Step2: Deploy Web App to Vercel and deploy to Azure

1. deploy `preview` when merge PR into main branch and push commit to main branch, see [./.github/workflows/deploy-preview.yml](./.github/workflows/deploy-preview.yml)

2. deploy `prod` when publish a release, see [./.github/workflows/deploy-prod.yml](./.github/workflows/deploy-prod.yml)

## File Structure

```
.
├── .github
│   └── ... // CI/CD
├── infra
│   └── ... // Infrastructure as Code
├── ...
│   └── ... // Others source code
```