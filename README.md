# Store Terraform state in Azure Storage

https://learn.microsoft.com/en-us/azure/developer/terraform/store-state-in-azure-storage?tabs=azure-cli

1. Configure your environment
Azure subscription: If you don't have an Azure subscription, create a free account before you begin.
Configure Terraform: If you haven't already done so, configure Terraform using one of the following options:

- Configure Terraform in Azure Cloud Shell with Bash
- Configure Terraform in Azure Cloud Shell with PowerShell
- Configure Terraform in Windows with Bash
- Configure Terraform in Windows with PowerShell


2. Configure remote state storage account
Before you use Azure Storage as a backend, you must create a storage account.

- modify terraform.tfvars file

Key points:

Azure storage accounts require a globally unique name. To learn more about troubleshooting storage account names, see Resolve errors for storage account names.
Terraform state is stored in plain text and may contain secrets. If incorrectly secured, this could result in unauthorised access to systems and data loss.
In this example, Terraform authenticates to the Azure storage account using an Access Key. In a production deployment, it is recommended to evaluate the available authentication options supported by the azurerm backend and to use the most secure option for your use case.
In this example, public network access is allowed to this Azure storage account. In a production deployment, it is recommended to retrict access to this storage account using a storage firewall, service endpoint, or private endpoint.
Azure storage accounts require a globally unique name. To learn more about troubleshooting storage account names, see Resolve errors for storage account names.

3. Configure terraform backend state

To configure the backend state, you need the following Azure storage information:

- storage_account_name: The name of the Azure Storage account.
- container_name: The name of the blob container.
- key: The name of the state store file to be created.
- access_key: The storage access key.
- Each of these values can be specified in the Terraform configuration file or on the command line. We recommend that you use   an environment variable for the access_key value. Using an environment variable prevents the key from being written to       disk.

please, visit https://gdservices.io/blog/ for more information
