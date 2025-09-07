# CI/CD Pipeline with Azure DevOps Classic Editor


## This repository showcases a multi-stage CI pipeline implemented in Azure DevOps Classic Editor, running on a local Ubuntu self-hosted agent. The pipeline integrates several DevOps tools to automate infrastructure provisioning, security validation, and cost analysis.

### This project focuses on CI for Infrastructure-as-Code (IaC)


1.**Automation** – reducing manual effort and human error

2.**Security** – detecting misconfigurations before deployment

3.**Cost-awareness** – embedding FinOps into DevOps workflows

4.**Flexibility** – leveraging Azure DevOps with a local Linux agent



### Pipeline Overview

#### Tools & Integrations

    1. Terraform Init : Initializes Terraform backend and modules using the TerraformCLI task.

    2. Terraform Validate : Validates Terraform configuration and syntax using the TerraformCLI task.

    3. Terraform Plan : Generates an execution plan using the TerraformCLI task.

    4. Terraform : For IaC provisioning and validation.

    5. TFSEC : Security scanning for Terraform code.

    6. TFLint : Linting to enforce Terraform best practices.

    7. Infracost : Cloud cost estimation before provisioning



## In modern software delivery, Continuous Integration (CI) and Continuous Deployment (CD) are essential for ensuring that code changes are automatically built, tested, and validated before being promoted to production. While YAML-based pipelines are becoming the industry standard, the Azure DevOps Classic Editor still provides a powerful, visual way to design CI/CD workflows—making it ideal for learning, prototyping, and rapid iteration.



<img width="1920" height="1200" alt="Screenshot from 2025-08-30 20-46-48" src="https://github.com/user-attachments/assets/63a633a1-73ee-444b-8a2f-633fa61cb878" />
