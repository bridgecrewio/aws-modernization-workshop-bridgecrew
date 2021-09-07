---
title: "Module - Automate"
chapter: true
weight: 201
pre: "<b>5 </b>"
---

# MODULE - AUTOMATE
In the previous section, we used the Checkov CLI to do some quick scanning before committing a change into the code repository. That’s great for checking work here and there but forcing every developer to run a scan on their machines before every single commit isn’t reasonable or feasible. To continuously audit code, automation and built-in workflows are key. With Bridgecrew, you can automate your infrastructure scanning along with the rest of your unit and integration testing by embedding it into your version control system and CI/CD pipeline.

This module will show you how to prevent cloud security issues from being deployed by integrating Bridgecrew with both the AWS developer tools suite, and GitHub Actions.

## Module Learning Objectives
- Creating your own CloudFormation demo repository on GitHub
- Setting up AWS CodeBuild
- Setting up AWS CodePipeline
- Adding Bridgecrew scanning of CloudFormation manifests into CodeBuild
- Adding Bridgecrew scanning of CloudFormation manifests with GitHub Actions