---
title: "Terraform Environment"
chapter: true
weight: 5
pre: "<b>3.1 </b>"
---

## Terraform Environment Setup

You’ll use the Terraform CLI locally as well as Terraform Cloud. If you don’t have the Terraform CLI installed on your computer, see the [instructions here](https://learn.hashicorp.com/tutorials/terraform/install-cli).

Terraform Cloud (TFC) is a self-service SaaS platform that extends the capabilities of the open source Terraform CLI. It’s free for basic usage, but we’ll be leveraging advanced features, such as Sentinel, that will require a paid subscription or trial. Sign up for Terraform Cloud [here](https://app.terraform.io/signup) and log in using your CLI.

```
terraform login
```