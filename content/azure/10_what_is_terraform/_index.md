---
title: "Infrastructure as Code using Terraform"
chapter: false
weight: 3
pre: "<b>2 </b>"
---

## What is infrastructure as code anyway?

Infrastructure as code (IaC) frameworks such as ARM and HashiCorp Terraform make cloud provisioning scalable and straightforward by leveraging automation and code. Defining our cloud infrastructure in code simplifies repetitive DevOps tasks and gives us a versioned, auditable single source of truth for our environment configurations.

HashiCorp Terraform is a multi-cloud IaC tool that allows us to define how we want our infrastructure to look, and it will generate all of the commands to make that happen. Any changes we want to make, such as adding more instances with the same configurations, Terraform will handle for us after we define the changes in our template. 

For strictly demonstration purposes, the following Terraform resource block creates an Azure Storage Account without any CLI or GUI commands:

```hcl
resource "azurerm_storage_account" "example" {
  name                     = "storageaccountname"
  resource_group_name      = "resourcegroup"
  location                 = "West US"
  account_tier             = "Standard"
  account_replication_type = "LRS"
}
```

After performing `terraform init`, we can provision a Storage Account with the following command:

```bash
terraform apply
```

Any changes we make to that file, such as adding tagging or changing the networking rules, will just require another `terraform apply` command to update our bucket.

### Security and Terraform

Another benefit of using Terraform to define our infrastructure is that we can audit the code for misconfigurations before any infrastructure is created. That enables us to bake security into development processes and prevent infrastructure issues before they open an S3 bucket to the world.

That’s why we scan our Terraform templates for vulnerabilities before deployment. With Bridgecrew, we can automate this whole process, from finding the bugs to fixing them.

**In this workshop, we’re doing exactly that. So let’s get started!**