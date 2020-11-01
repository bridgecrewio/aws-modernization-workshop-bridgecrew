---
title: "One | Finding CloudFormation misconfigurations locally"
chapter: true
weight: 10
---

# Finding cloud misconfigurations and policy violations in AWS resources and CloudFormation code

### Module Learning Objectives

- Creating a demo CloudFormation repository using GitHub by cloning CFNGoat.
- Scan a CloudFormation template for misconfigurations locally.


### Analyzing CloudFormation configuration with Bridgecrew

In this module, we’ll start by testing Bridgecrew CLI with the CfnGoat template, Bridgecrew’s vulnerable-by-design project created to help demonstrate common errors and security best practices in AWS CloudFormation.

You already cloned the CFNGoat repository in the getting started module, however if you need to do so again, use the following:

```
git clone https://github.com/bridgecrewio/cfngoat.git
cd cfngoat
git status
```