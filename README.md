# Azure Data Management Pipeline Automation with Terraform

This repository contains Terraform scripts designed to automate the setup of data management pipelines in Azure. It provisions a data factory and a storage account, essential components for managing and processing large datasets efficiently.

## Project Structure

This project is structured as follows:
- `main.tf`: The main Terraform configuration file that calls modules and sets up providers.
- `modules/`: Contains submodules used by the main Terraform configuration.
  - `data_factory/`: Module for Azure Data Factory resources.
    - `data_factory/data_factory.tf`: Terraform configuration for Data Factory.
    - `data_factory/variables.tf`: Variables specific to the Data Factory module.
  - `storage_account/`: Module for Azure Storage Account resources.
    - `storage_account/storage_account.tf`: Terraform configuration for Storage Account.
    - `storage_account/variables.tf`: Variables specific to the Storage Account module.
- `variables.tf`: Defines variables used in the `main.tf`.
- `variables.tfvars`: Values for the variables that will be passed to the Terraform configuration.
- `plan.out`: Output from the `terraform plan` command, useful for reviewing changes before applying them.
- `terraform.tfstate`: Terraform state file, tracks the state of your managed infrastructure and configuration.
- `terraform.tfstate.backup`: Backup of the state file.

## Prerequisites

Before you begin, ensure you have the following installed:
- Terraform (version 0.12 or newer)
- Access to an Azure subscription
- Azure CLI, authenticated to your Azure subscription

## Usage

### Cloning the Repository

Start by cloning the repository to your local machine:

```bash
git clone https://github.com/drjodyannjones/azure-data-management-pipeline.git
cd azure-data-management-pipeline
```

### Initializing the Project

Initialize the Terraform environment:

```bash
terraform init
```

This command installs necessary Terraform providers and modules.

### Planning Infrastructure Changes

Create an execution plan, which lets you preview changes before applying them:

```bash
terraform plan -var-file="variables.tfvars" -out plan.out
```

### Applying Changes

Apply the changes required to reach the desired state of the configuration:

```bash
terraform apply "plan.out"
```

### Viewing Current State

To see the current state of your managed infrastructure:

```bash
terraform show
```

### Modifying or Refactoring

If you need to refactor or rename resources, Terraform's `state mv` command can be useful:

```bash
terraform state mv [options] SOURCE DESTINATION
```

### Destroying Infrastructure

To destroy all resources managed by a Terraform module:

```bash
terraform destroy -var-file="variables.tfvars"
```

This command is irreversible and should be used with caution.

## Contributing

Contributions to this project are welcome! Please fork the repository and submit pull requests with any enhancements. For any questions, you can contact me at drjodyannjones@gmail.com.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details.

## Authors

- **Jody Ann Jones** - *Initial work* - [drjodyannjones](https://github.com/drjodyannjones)

## Acknowledgments

- Yusuf Ganiyu, for his mentorship and invaluable insights. Connect with Yusuf on [LinkedIn](https://www.linkedin.com/in/yusuf-ganiyu-b90140107/).
```

