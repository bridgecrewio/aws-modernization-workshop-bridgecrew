---
title: "Module - Automate"
chapter: true
weight: 201
pre: "<b>5 </b>"
---

# MODULE - AUTOMATE

In the previous section, we used Checkov and VS Code extension to scan our Terraform templates locally. However, we can’t expect consistency if the process is one-off. We need to continuously scan the code for misconfigurations before it makes its way into production.

That’s where automating IaC scanning in our continuous integration/continuous delivery (CI/CD) pipeline comes in. With Bridgecrew, we can scan templates before they are committed to our VCS when you run other unit and integration testing, or in your VCS. This allows you to provide automated feedback as a part of a CI run and, if in blocking mode, block misconfigured code.

In this module, we’ll add in automated scans using GitHub Actions and with Terraform Cloud.

## Module Learning Objectives
- Set up the Bridgecrew GitHub Action
- Set up the Bridgrew GitHub Application
- Set up the Bridgecrew and Terraform Cloud integration
- Run a scan