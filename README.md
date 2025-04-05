# Azure: Kaggle Dataset Extract

## Introduction

This project documents how to use Kaggle API to extract datasets using Databricks and load into Azure Data Lake Storage Gen 2

## Getting Started
### 1. Provisioning Azure Resources
- Create a storage account
- Create a Databricks workspace
- Create a key vault

### 2. Configuring Key Vault
- Under Settings >> Access Configuration, use 'Vault access policy'
- Provide Secret permissions to yourself (not the Databricks service principal)

### 3. Setting up a Service Principal
- Register a new application (e.g databricks-service-principal) in Microsoft Entra ID
- Go to the storage account and provide a Storage Data Contributor role to the Service Principal

### 4. Setting up Kaggle API token
- Go to your Kaggle profile setting and create a new token
<img width="755" alt="image" src="https://github.com/user-attachments/assets/1f487996-99a8-4d2c-9a99-89da65848e3b" />

### 5. Create Secrets in Key Vault
- Create secrets to store the following:
  - Service Principal credential
  - Kaggle API key

### 6. Configuring Azure Databricks
- Create secret scope
- Download and import the dbc file (in the src folder) to the databricks workspace

## Services Used

- Azure Databricks
- Azure Data Lake Storage Gen 2
- Azure Key Vault

## Resources

- [DP-203: 33 - Connecting to ADLSg2 from Azure Databricks](https://www.youtube.com/watch?v=GEh4D7tq3nU&list=PLuQSde7Xvu7DCRenR1otgxAplTtnzKO9e&index=34&t=1017s&ab_channel=TybulonAzure)
- [Databricks documentation on Secret Scope](https://docs.databricks.com/aws/en/security/secrets/?language=Databricks%C2%A0workspace%C2%A0UI)
