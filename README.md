# CI/CD Pipeline with Azure DevOps Classic Editor


## This repository showcases a multi-stage CI pipeline implemented in Azure DevOps Classic Editor, running on a local Ubuntu self-hosted agent. The pipeline integrates several DevOps tools to automate infrastructure provisioning, security validation, and cost analysis.


### Pipeline Overview

#### Tools & Integrations

    -Terraform Init : Initializes Terraform backend and modules using the TerraformCLI task.

    -Terraform : For IaC provisioning and validation

    -TFSEC : Security scanning for Terraform code

    -TFLint : Linting to enforce Terraform best practices

Infracost – cloud cost estimation before provisioning
## In modern software delivery, Continuous Integration (CI) and Continuous Deployment (CD) are essential for ensuring that code changes are automatically built, tested, and validated before being promoted to production. While YAML-based pipelines are becoming the industry standard, the Azure DevOps Classic Editor still provides a powerful, visual way to design CI/CD workflows—making it ideal for learning, prototyping, and rapid iteration.

