---
title: "Cleanup"
chapter: true
weight: 1000
pre: "<b>8 </b>"
---

## Azure Cleanup

{{% notice warning %}} In order to prevent charges to your account we recommend cleaning up the infrastructure that was created. If you plan to keep things running so you can examine the workshop a bit more please remember to do the cleanup when you are done. It is very easy to leave things running in an Azure account, forget about it, and then accrue charges. {{% /notice %}}

### Terraform

If you deployed any infrastructure using the Terraform CLI, make sure to run `terraform destroy`. This includes both the example pull request template and the Bridgecrew Azure integration.
If you deployed any infrastructure using Terraform Cloud, go into the workspace and select “Settings” -> “Destruction and Deletion” -> “Queue destroy plan”.

### Bridgecrew Cleanup

The Bridgecrew account you created is free to use for up to 50 cloud resources, you can leave your Azure account integrated from the runtime section of this workshop to automatically detect infrastructure security issues in your account. The GitHub integration will also continue to scan pull requests to detect, annotate and prevent new infrastructure as code issues.

These integrations can be disabled from the [Bridgecrew platform integrations](https://www.bridgecrew.cloud/integrations) page if need be.