---
title: "Cleanup"
chapter: true
weight: 1000
pre: "<b>8 </b>"
---

## AWS Cleanup
{{% notice warning %}} In order to prevent charges to your account we recommend cleaning up the infrastructure that was created. If you plan to keep things running so you can examine the workshop a bit more please remember to do the cleanup when you are done. It is very easy to leave things running in an AWS account, forget about it, and then accrue charges. {{% /notice %}}

### CodePipeline
In the AWS console, go to [AWS CodePipeline](https://console.aws.amazon.com/codesuite/codepipeline/), and delete the `scan-cfngoat-bridgecrew` pipeline we created.

### CodeBuild
 [AWS CodeBuild](https://aws.amazon.com/codebuild/), and delete the `bridgecrew-tutorial` project we created.

### IAM Role
Finally, remove the IAM role we created:
 - `codebuild-bridgecrew-tutorial-service-role`


## Bridgecrew Cleanup
The Bridgecrew account you created is free to use for up to 100 cloud resources, you can leave your AWS account integrated from the [runtime section of this workshop](../30_module_three/3004_bridgecrew_automate_add_runtime.html) to automatically detect infrastructure security issues in your account. The GitHub integration will also continue to  scan pull requests to detect, annotate and prevent new infrastructure as code issues. 

You may want to check out the following resources:

[IAM Insights: Automated right-sizing with policy-as-code](https://bridgecrew.io/blog/iam-insights-automated-right-sizing-for-iam-policy-code/)
[Scanning AWS Cloud Development Kit (CDK) with Bridgecrew](https://bridgecrew.io/blog/cloudformation-aws-cdk-scanning-security-compliance/)
[Bridgecrew Documentation](https://docs.bridgecrew.io/docs)

These integrations can be disabled from the [Bridgecrew platform integrations page](https://www.bridgecrew.cloud/integrations/Github) if need be.

{{% children showhidden="false" %}}