# Localstack DevOps Pipeline

This project demonstrates a complete DevOps pipeline using **Jenkins**, **Docker Compose**, **Terraform**, and **Localstack**. The pipeline builds a React app and provisions a DynamoDB table using Infrastructure as Code, all running locally with no AWS costs.

---

## Features
- **CI/CD:** Jenkins automates the build and infrastructure provisioning.
- **IaC:** Terraform manages a DynamoDB table (guaranteed to work with Localstack).
- **Cloud Emulation:** Localstack simulates AWS services for safe, free testing.
- **Open Source Ready:** No secrets or hardcoded credentials; all configs and code are in the repo.
- **No CloudZero SaaS:** The project name is for branding only; no CloudZero service is used.

---

## Tech Stack
- **Jenkins** (CI/CD)
- **Terraform** (Infrastructure as Code)
- **Localstack** (AWS emulation)
- **React** (static site)
- **Docker Compose** (orchestration)

---

## How to Run
1. **Clone the repo:**
   ```bash
   git clone https://github.com/supritg/cloudzero-devops-pipeline.git
   cd cloudzero-devops-pipeline
   ```
2. **Start the stack:**
   ```bash
   docker-compose up -d --build
   ```
3. **Access Jenkins:**
   - Visit [http://localhost:8080](http://localhost:8080)
   - Unlock Jenkins and set up your admin user (first run only)
4. **Run the pipeline:**
   - Trigger the pipeline job in Jenkins
   - The pipeline will:
     - Build the React app
     - Provision a DynamoDB table in Localstack using Terraform

---

## Project Structure
```
localstack-devops-pipeline/
├── Jenkinsfile           # Jenkins pipeline definition
├── docker-compose.yml   # Orchestrates Jenkins & Localstack
├── terraform/           # Terraform code for DynamoDB
│   └── main.tf
├── website/             # React app source
└── README.md            # Project documentation
```

---

## Notes
- **No AWS costs:** All infra is provisioned in Localstack (AWS emulator).
- **Switch to real AWS:** To use real AWS, update the Terraform provider and set real credentials.
- **Open source:** Ready for community contribution and demo.
- **No CloudZero SaaS:** This project does not use any CloudZero product or service.

