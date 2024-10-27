# Multi-Tier-App-DevOps-Pr
This is for cicd pipeline purpose.

# Application Architecture:

A front-end web app in Python which lets you vote between two options

A Redis which collects new votes

A .NET worker which consumes votes and stores them

A Postgres database backed by a Docker volume

A Node.js web app which shows the results of the voting in real time.
<img width="813" alt="17300488945509007546133056995801" src="https://github.com/user-attachments/assets/b37dbc40-3393-4dec-8a02-d307673c4dd3">

# CI/CD ![IMG_20241027_225736](https://github.com/user-attachments/assets/6893a6fd-647d-43ef-85ab-ca1a41a4fc7e)

# Pipeline Stages  
1. Build
2. Push
3. Update

# Steps for Project 

**CI Setup in Azure Devops**

Step 1: Containerizing Microservices with Dockerfile 

Step 2: Importing the GitHub Repository to Azure Repos 

Step 3: Creating the CI Pipeline in Azure DevOps 
1. Create a resource group in Azure.
2. Set up Azure Container Registry (ACR) within that resource group.
3. Create a self-hosted Virtual Machine (VM) in Azure to serve as the agent for running the CI pipeline.

![17300507895607600823993828335404](https://github.com/user-attachments/assets/9b598c14-510c-43a9-861e-0c3f5917f415)

Step 4: Authorizing the Azure Agent Setting Up Agent Pool 

![17300508609011657142845370119542](https://github.com/user-attachments/assets/7db74947-0e8e-44fc-bf8c-b467284d9784)

**CD Setup**

# Setting Up AKS

Start by creating an AKS cluster in Azure. You’ll also need to set up Virtual Machine Scale Sets as node pools within the AKS cluster. 

# Configuring ArgoCD

ArgoCD will continuously monitor the Azure repository for any changes.

![17300510505533191572922265863741](https://github.com/user-attachments/assets/516b532c-5c05-4f9c-ae74-992156a09349)

To access the ArgoCD UI, you’ll need to expose the ArgoCD server externally using a LoadBalancer or NodePort. Make sure to configure the necessary network security rules to allow inbound traffic on the required port.

![1730051090616630287666374217998](https://github.com/user-attachments/assets/9071f8b0-b78d-4cff-ae47-856a3a2c43e2)

# Automating Image Updates with Shell Scripts 

We’ll create a shell script that updates the Kubernetes deployment YAML file whenever a new image is built. This script will ensure that the correct image version is always deployed to the AKS cluster.
