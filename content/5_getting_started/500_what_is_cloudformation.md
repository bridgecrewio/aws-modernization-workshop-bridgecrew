---
title: "What is CloudFormation?"
chapter: true
weight: 3
---

## What is CloudFormation and Infrastructure as Code?

AWS CloudFormation makes cloud provisioning simple and scalable by leveraging both automation and configuration as code. Defining your cloud infrastructure and applications as code simplifies repetitive DevOps tasks and gives you a single source of truth for app and environment configuration.

This makes it more important to make sure your infrastructure as code (IaC) resources follow security best practices—your CloudFormation configuration is now another part of your codebase, and should be tested and scanned for errors and risks just like any other code review.

### Tracked, Versioned cloud resources

CloudFormation lets you define your AWS infrastructure with templates, which you can check into version control or store in S3 buckets.
CloudFormation templates are JSON or YAML files. For instance, the following template defines an S3 bucket:

```json
{

  "AWSTemplateFormatVersion" : "2010-09-09",
  "Description" : "AWS CloudFormation Sample Template: Sample template showing how to create a publicly accessible S3 bucket.",
  "Resources" : {
    "S3Bucket" : {
      "Type" : "AWS::S3::Bucket",
      "Properties" : {
        "AccessControl" : "PublicRead",
        "WebsiteConfiguration" : {
          "IndexDocument" : "index.html",
          "ErrorDocument" : "error.html"
         }
      },
      "DeletionPolicy" : "Retain"
    }
  },
  "Outputs" : {
    "WebsiteURL" : {
      "Value" : { "Fn::GetAtt" : [ "S3Bucket", "WebsiteURL" ] },
      "Description" : "URL for website hosted on S3"
    },
    "S3BucketSecureURL" : {
      "Value" : { "Fn::Join" : [ "", [ "https://", { "Fn::GetAtt" : [ "S3Bucket", "DomainName" ] } ] ] },
      "Description" : "Name of S3 bucket to hold website content"
    }
  }
}
```

You can create this bucket in seconds using the AWS CLI (not required for the workshop):
```bash
aws cloudformation create-stack --stack-name myexamplestack --template-body file:///home/example/mytemplate.json
```
The benefit of using CloudFormation to define your infrastructure is that it allows you to audit the templates before they are deployed. Finding potential security issues before the infrastructure becomes *real*, you’re now able to bake best practices for security into your development and deployment lifecycle.

With Bridgecrew, you can automate the scanning of your IaC codebase and deployed resources, find misconfigurations, and fix issues fast. 

We'll walk through the process of configuring Bridgecrew to scan a CloudFormation deployment, run the scans, find issues, and fix them!

### Thats enough context, hit next to get started!
