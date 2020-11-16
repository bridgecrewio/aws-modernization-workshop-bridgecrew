---
title: "Module 2 - Automate"
chapter: true
weight: 20
---

# MODULE 2
In the previous section, we used the Bridgecrew CLI to do some quick scanning before committing a change into the code repository. That’s great for checking work here and there but  forcing every developer to run a scan on their machines before every single commit isn’t reasonable or feasible. To continuously audit code, automation and built-in workflows are key. With Bridgecrew, you can automate your infrastructure scanning along with the rest of your unit and integration testing by embedding it into your version control system and CI/CD pipeline.

This module will show you how to prevent cloud security issues from being deployed   by integrating Bridgecrewwith the AWS developer tools suite. 

## Module Learning Objectives
- Creating your own CloudFormation demo repository on GitHub
- Setting up AWS CodeBuild
- Setting up AWS CodePipeline
- Adding Bridgecrew scanning of CloudFormation manifests into CodeBuild