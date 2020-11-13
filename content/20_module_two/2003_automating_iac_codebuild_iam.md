---
title: "Edit IAM for CodeBuild"
chapter: true
weight: 23
---

## Edit AWS IAM permissions to enable CodeBuild

To give CodeBuild access to our Bridgecrew API secret we stored in AWS System Manager, we’ll need to add more permissions to the default IAM role created for new CodeBuild environments.

In the [AWS IAM Dashboard](https://console.aws.amazon.com/iam/home), find the role called `codebuild-bridgecrew-tutorial-service-role`

![AWS IAM Policy Visual Editor](./images/codebuild-create-project-github-iam-12.png "AWS IAM Policy Visual Editor")

Select the role, then click select  **Add Inline Policy** from the right hand side.

This will bring up the "*create policy visual editor*", for **Service**, select **Systems Manager** in the search box, then chose the **GetParameters** and **GetParameter** Actions.

![AWS IAM Dashboard](./images/codebuild-create-project-github-iam-15.png "AWS IAM Dashboard")

Under **Resources**, choose **Specific** and select **Add ARN**. Fill in the same region  you’ve created your CodeBuild project and leave the account number as the default. Type `bridgecrew_api_key` as the parameter name to match the name we gave the key in the `aws` CLI command we used earlier.


![AWS IAM Dashboard](./images/codebuild-create-project-github-iam-14.png "AWS IAM Dashboard")

Select **Add** and once you’ve reviewed your new policy, **Create policy**:

![AWS IAM Dashboard](./images/codebuild-create-project-github-iam-16.png "AWS IAM Dashboard")

We’re now ready to tie this all together with AWS CodePipeline!
