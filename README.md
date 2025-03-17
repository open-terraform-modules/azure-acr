# azure-acr
Terraform module for provisioning an Azure Container Registry (ACR). Supports different SKU options and authentication settings for container image storage.
## Usage

```hcl
module "acr" {
    source              = "github.com/open-terraform-modules/azure-acr"
    resource_group_name = "my-resource-group"
    name                = "myacr"
    location            = "West Europe"
    sku                 = "Standard"
    admin_enabled       = true
        tags                = {
        environment = "dev"
        project     = "example"
    }
}
```

## Inputs

| Name                | Description                                      | Type    | Default | Required |
|---------------------|--------------------------------------------------|---------|---------|----------|
| name            | The name of the Azure Container Registry.        | `string` | n/a     | yes      |
| resource_group_name | The name of the resource group in which to create the ACR. | `string` | n/a     | yes      |
| location            | The location of the resource group       | `string` | n/a     | yes      |
| sku                 | The SKU of the Azure Container Registry.         | `string` | `Basic` | no       |
| admin_enabled       | Specifies whether the admin user is enabled.     | `bool`   | false   | no       |

## Outputs

| Name       | Description                           |
|------------|---------------------------------------|
| acr_id     | The ID of the Azure Container Registry. |
| login_server | The URL that can be used to log in to the ACR. |

## Contributing

To contribute to this project, follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Open a pull request.

## Author

This module is maintained by [Andres Montealegre](mailto:montealegre.af@gmail.com).