---
title: "Pipeline Results"
chapter: true
weight: 206
pre: "<b>5.5 </b>"
---

## Reviewing our pipeline results
Your new CodePipeline will immediatley start running your CodeBuild job against the latest commit in your GFNGoat Repository.

You will be taken to the Pipeline Jobs page where you will see the progress as CodeBuild checks out the latest commit from GitHub and starts our job to run Bridgecrew against the CloudFormation configuration.

Below we see the Pipeline sucessfully created and starting to run:

![AWS CodeBuild Run Status](./images/runpipeline-1.png "AWS CodeBuild Run Status")

If everything goes as intended, the pipeline should fail at the build stage since the CfnGoat code is purposely designed with security flaws. Only when the issues are fixed will the pipeline status turn to green.


By blocking the committed code from making it to any “Deploy” steps, we can prevent vulnerable infrastructure from making its way to any AWS account, be it test or prod and helping to satisfy the requirements of the [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)


![AWS CodeBuild Run Failed](./images/runpipeline-3.png "AWS CodeBuild Run Failed")

Dig into the failed build **Details** and select the link to **execution details**:

![AWS CodeBuild Run Failed](./images/runpipeline-4.png "AWS CodeBuild Run Failed")

Here we are provided a link to our build logs, revealing the security violations and why Bridgecrew blocked the build:

![AWS CodeBuild Run Failed](./images/runpipeline-5.png "AWS CodeBuild Run Failed")


Navigating to [*Codebuild > Report Group*](https://console.aws.amazon.com/codesuite/codebuild/), we can also see a simple graph of failed and passed checks with an easier-to-read output of all failed checks. 

![AWS CodeBuild JUnit output](./images/junit-codebuild-output-report.png) "AWS CodeBuild JUnit output)

## Congratulations!
You’ve just automated security scanning of your infrastructure as code into a developer-friendly CI/CD pipeline.

In the next module, we’ll look at how to investigate and fix these issues, as well as providing more tips for integrating security into the developer workflow without causing friction.

