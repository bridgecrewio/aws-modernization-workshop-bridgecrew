---
title: "Two | Automating detection and enforcement"
chapter: true
weight: 20
---

# Preventing cloud security issues from being deployed through automated policy enforcement

## Module Learning Objectives
- Setting up AWS CodeBuild
- Setting up AWS CodePipeline
- Adding Bridgecrew scanning of CloudFormation manifests into CodeBuild
- Reviewing buildtime misconfigurations with Bridgecrew
- Automating fixes and verification through pull requests

## Integrating Bridgecrew with AWS dev tools suite

In the previous section, we used the Bridgecrew CLI to do some quick scanning before committing a change into the code repository. However, forcing every developer to run a scan in their machines ad hoc isn’t conducive. We need a smarter approach, one that continuously audits code.

Bridgecrew supports all popular version control systems and CI/CD platforms. We can, for instance, set up Bridgecrew to run every time a developer commits into a GitHub repository.

This section will show you how to continuously scan CloudFormation templates by integrating Bridgecrew with AWS DevOps tooling, AWS CodeBuild and AWS CodePipeline.

The integration takes three steps:

- Create your own CFNGoat fork on Github.
- Configure CodeBuild to audit your code.
- Set up CodePipeline to rerun the audit on every change.



