---
title: "CloudFormation Overview?"
chapter: true
weight: 3
---

## How do CloudFormation and infrastructure as code work?

Infrastructure as code (IaC) frameworks such as AWS CloudFormation, Terraform, and Pulumi make cloud provisioning simple and scalable by leveraging automation and code. Defining your cloud infrastructure in code simplifies repetitive DevOps tasks and gives you a single source of truth for your app and environment configuration.

AWS CloudFormation enables you to define your AWS infrastructure with templates, which you can check into version control or store in S3 buckets. CloudFormation templates are JSON or YAML files. For instance, the following template defines an S3 bucket:

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

Using the AWS CLI, you can provision the above bucket in seconds:
*(This is an example, not required for the workshop)*

```bash
aws cloudformation create-stack --stack-name myexamplestack --template-body file:///home/example/mytemplate.json
```

## Security and CloudFormation IaC
The benefit of using CloudFormation to define your AWS infrastructure is that it allows you to audit templates before they’re deployed. That will enable you to bake security best practices into your development and deployment lifecycle and finding potential security and compliance issues before the infrastructure becomes real.

CloudFormation gives us total control to create, change, and delete resources in AWS. With CloudFormation, it’s easy to pick and deploy any of the hundreds of templates readily available from the AWS sample templates. Because these templates are built solely with functionality in mind, it’s also easy to forget important security configuration and end up having an insecure service running in production.

That’s why scanning your CloudFormation templates for vulnerable infrastructure before deployment is so important. With Bridgecrew, you can automate the scanning of your IaC codebase and cloud resources to both find and fix misconfigurations. 

**In this workshop, we’re doing exactly that. So let’s get started!**
