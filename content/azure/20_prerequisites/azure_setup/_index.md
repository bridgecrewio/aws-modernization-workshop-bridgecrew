---
title: "Azure Environment"
chapter: false
weight: 6
pre: "<b>3.2 </b>"
---

{{% notice warning %}}
Disclaimer: We will be using an Azure account to show Bridgecrew’s runtime capabilities and drift detection. If you follow along, remember to shut down any Azure services to avoid additional fees.
{{% /notice %}}

## Azure Environment setup

{{% notice info %}}
Your account must have the ability to create new AD roles and scope other IAM permissions.
{{% /notice %}}

1. If you don't already have an Azure account with Administrator access: [create
one now by clicking here](https://azure.microsoft.com/en-us/free/)

1. Once you have an Azure account, ensure you are following the remaining workshop steps as an AD user with administrator access to the Azure account: [View permissions for your user](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview). Alternatively, you can use a service principal with enough access to perform Terraform tasks: [See the Terraform docs for more info](https://registry.terraform.io/providers/hashicorp/azuread/latest/docs/guides/service_principal_configuration)
