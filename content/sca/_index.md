---
title: "Capture the Flag Challenge - Software Composition Analysis (SCA)"
chapter: true
weight: 1
---

# Welcome!


Break the Bank CTF!

Log4janky Bank has an online banking application in production, but their IT infrastructure is behind. They are vulnerable to the infamous Log4shell vulnerability.

In this workshop, we'll teach you modern hacking methods to break into the Bank's Kubernetes infrastructure and from there find the flags to complete the mission!

Once we have the flags, we will swap out our black hats for white and show how the Bank could have quickly used open source and automation to find and fix the vulnerabilities both in their application and infrastructure stack.

## Learning Objectives

Here you will play two roles. First, the stealthy Black Hat hacker looking to compromise our Bank. Second, you will play the intrepid White Hat defender looking to deployment automation to find, fix and secure our Bank. By solving and walking through this challenge, you will be able to:

## Topics Covered

### Black Hat
 - Discover the Log4j vulnerability
 - Learn the anatomy of a Log4shell hack and execute it against our vulnerable Bank
 - Create a reverse shell to gain root access to the application container
 - Discover weaknesses in the containers deployment to get access to the EKS node/cluster

### White Hat
 - Use the open source tool Checkov to find all vulnerabilities in the application and deployment
 - Fix the issues and redeploy a secure Bank using CodeBuild/CodeCommit/CodePipeline
 - Technical knowledge prerequisites
 
## Prerequisites
 - Previous hacking knowledge is not required
 - Knowledge of Linux bash shell commands, extremely helpful
