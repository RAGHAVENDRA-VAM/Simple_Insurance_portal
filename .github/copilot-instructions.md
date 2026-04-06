#  DEVOPS GENERATOR – REACT APP (AZURE) – PRODUCTION READY

When user types any of these keywords:

* "setup react azure devops pipeline"
* "generate full devops for react azure"
* "create terraform ci cd react azure"

 Generate a complete production-ready DevOps setup with the following standards:

---

#  PROJECT STRUCTURE

Create:

.
├── azure/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│
├── .github/
│   └── workflows/
│       ├── ci.yml
│       ├── cd.yml
│
├── security/
│   └── sast.yml
│
└── README.md

---

#  TERRAFORM REQUIREMENTS (AZURE)

Use azurerm provider and create:

1. Resource Group
2. App Service Plan (Linux, B1 or Free tier)
3. Azure Web App for React app

Standards:

* Use variables.tf for all configurable values
* Use outputs.tf for app URL
* Use naming convention: <project>-<env>-<resource>
* Add tags (env, project, owner)

---

#  SECURITY (SAST)

Use GitHub CodeQL for JavaScript

Requirements:

* Initialize CodeQL
* Run analysis after build
* Fail pipeline on high severity issues

---

#  CI PIPELINE (ci.yml)

Use GitHub Actions.

Standards:

* YAML must follow proper indentation (2 spaces)
* Use reusable steps
* Use official actions only
* Add clear step names

Pipeline Requirements:

Trigger:

* push to main
* pull_request

Steps:

1. Checkout code
2. Setup Node.js (version 18)
3. Cache node_modules
4. Install dependencies using npm ci
5. Run lint (eslint)
6. Run tests (npm test)
7. Build app (npm run build)
8. Run CodeQL SAST

Artifacts:

* Store build folder

---

#  CD PIPELINE (cd.yml)

Trigger:

* After CI success (workflow_run)

Standards:

* Use environments (production)
* Add deployment name
* Use secrets securely

Steps:

1. Checkout code
2. Download build artifact
3. Deploy to Azure Web App using azure/webapps-deploy@v2

Requirements:

* Use publish profile from GitHub Secrets
* Do NOT hardcode secrets

---

#  YAML BEST PRACTICES

* Use 2 spaces indentation
* Use lowercase keys
* Use descriptive job and step names
* Avoid duplication
* Use variables where possible
* Add comments for each major step

---

#  SECRETS (DO NOT GENERATE VALUES)

Reference only:

* AZURE_WEBAPP_PUBLISH_PROFILE
* AZURE_CLIENT_ID
* AZURE_CLIENT_SECRET
* AZURE_TENANT_ID
* AZURE_SUBSCRIPTION_ID

---

#  README.md

Generate a README including:

* Project overview
* Setup steps
* Required secrets
* How pipeline works

---

#  OUTPUT FORMAT

* Generate ALL files with correct paths
* Each file must contain production-ready code
* Include comments explaining key sections
* Ensure no syntax errors

---

#  FINAL GOAL

User should be able to:

1. Push code
2. CI runs (build + SAST)
3. CD runs (deploy)
4. App available in Azure Web App

---
