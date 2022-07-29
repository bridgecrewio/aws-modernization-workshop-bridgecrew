---
title: "Cleanup"
chapter: true
weight: 1000
pre: "<b>8 </b>"
---

## AWS Cleanup

{{% notice warning %}} In order to prevent charges to your account we recommend cleaning up the infrastructure that was created. If you plan to keep things running so you can examine the workshop a bit more please remember to do the cleanup when you are done. It is very easy to leave things running in an AWS account, forget about it, and then accrue charges. {{% /notice %}}

### Terraform

If you deployed any infrastructure using the Terraform CLI, make sure to run `terraform destroy`.
If you deployed any infrastructure using Terraform Cloud, go into the workspace and select “Settings” -> “Destruction and Deletion” -> “Queue destroy plan”.

### IAM Role

Finally, remove the IAM role you created: - `codebuild-bridgecrew-tutorial-service-role`

### Bridgecrew Cleanup

The Bridgecrew account you created is free to use for up to 100 cloud resources, you can leave your AWS account integrated from the [runtime section of this workshop](../terraform/50_module_three/3003_bridgecrew_automate_add_runtime.html) to automatically detect infrastructure security issues in your account. The GitHub integration will also continue to scan pull requests to detect, annotate and prevent new infrastructure as code issues.

These integrations can be disabled from the [Bridgecrew platform integrations](https://www.bridgecrew.cloud/integrations/Github) page if need be.