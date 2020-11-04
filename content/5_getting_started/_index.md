---
title: "Getting Started"
chapter: false
weight: 2
---

We appreciate the double-edged sword when it comes to testing cloud security tools, with no appetite to expose production code repositories to new tools right away. We've tried to make it super easy to follow this workshop by providing our own, purposley-vulnerable set of CloudFormation templates, so that you can scan and automate infrastructure code without the added friction of integrating your own code.

## Learning Objectives
- Hands-on experience with both build-time and run-time configuration security and learn why addressing both leads to better security posture for your deployed infrastructure.
- Howto build a CI/CD pipeline with embedded policy governance enforced by security scanning tools.
- An insight into what happens if you don’t add infrastructure security to your pipeline because it’s always fun to break things!

## Prerequisites
- A basic understanding of git and github.com.
- An understanding of the role CI/CD pipelines play in a development lifecycle.
- Familiarity with AWS core concepts, such as IAM, regions, UI, CLI and API's.
- The AWS command line installed on your machine, `aws --version`
- An AWS account in which you will create an AWS Codebuild and AWS Codepipeline temporary environment.

You can test the current credentials cofigured for your local aws cli with the `aws sts get-caller-identity` command.

{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Bridgecrew and AWS services can be architected to build a solution while demonstrating best practices along the way. These examples, especially the intentionally vulnerable "CFNGoat" repository, are not intended for use in production environments.
</p>
{{% /notice %}}




