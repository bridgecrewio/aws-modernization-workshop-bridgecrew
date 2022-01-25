---
title: "Azure Environment"
chapter: false
weight: 6
pre: "<b>3.2 </b>"
---

{{% notice warning %}}
Disclaimer: We will be using an Azure account to show Bridgecrew’s runtime capabilities and drift detection. If you follow along, remember to shut down any Azure services at the end of the workshop to avoid additional fees.
{{% /notice %}}

## Azure Environment setup

{{% notice info %}}
Your account must have the ability to create new AD roles and scope other IAM permissions.
{{% /notice %}}

1. If you don't already have an Azure account with Administrator access: [create one now by clicking here](https://azure.microsoft.com/en-us/free/)

1. From your local terminal, make sure to install the [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/) and log in with `az login`

1. We need a [service principle](https://registry.terraform.io/providers/hashicorp/azuread/latest/docs/guides/service_principal_configuration) account for part of this workshop. Check that you are logged in as an AD user with administrator access to the Azure account: [View permissions for your user](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview).

1. From your terminal run `az account list` to list your connected accounts. Grab your `id` from that output and set your subscription with `az account set --subscription="<your_subscription_id>"`.

1. Generate a Service Principle with `az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/<your_subscription_id>"`. Save the output for later steps in the workshop.

![Azure Service Principle](images/code_ad_sp.png "Azure Service Principle")