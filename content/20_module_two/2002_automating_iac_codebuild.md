---
title: "Setup AWS Codebuild"
chapter: true
weight: 22
---

## Setup AWS CodeBuild for our CFNGoat fork.
AWS CodeBuild, paired with AWS CodePipeline is a CI/CD platform that can build projects, run jobs, and deploy infrastructure. We’re going to use it to scan the CloudFormation templates before deployment, allowing us to fail the build job and halt a deployment if there are any security violations in our CloudFormation code.

![AWS CodeBuild](./images/aws-codebuild-home.png "AWS CodeBuild")


We'll also send the results to the Brigecrew dashboard automatically, in order to maintain a view across all of our infrastructure projects and share visability throughout our organisation.

First, tell the Bridgecrew dashboard you're going to integrate AWS CodeBuild. To do this, open the integrations menu in your Bridgecrew account and select AWS Code Build, then **"Add Subscription"**

![Bridgecrew CodeBuild Integration](./images/bridgecrew-dash-add-codebuild.png "Bridgecrew CodeBuild Integration")

Run the command with your local `aws` cli as shown, this will save the Bridgecrew API key into your AWS System Manager's parameter store, so we can access it from our CodeBuild jobs later.

Also, copy the `buildspec.yaml` configuration to somewhere handy (or keep this bridgecrew tab open) we'll need it in just a little while.

{{% notice info %}}
<p style='text-align: left;'>
If the aws command fails, your IAM user may not have the correct permissions to create parameters in AWS Systems Manager (SSM). In that case, you’ll need to add write permissions to the user.

</p>
{{% /notice %}}

### New Codebuild Project

Now go to your [AWS CodeBuild service](https://aws.amazon.com/codebuild/) and select **Create a Build Project**:

![New CodeBuild Project](./images/codebuild-create-project-github-1.png "New CodeBuild Project")

Project Name: `bridgecrew-tutorial`

Description: `Automating IaC Security scanning with Bridgecrew and AWS`

Under the **Source** section, choose Github in the **Source Provider** dropdown, then **Connect using OAuth**, finally, press the **Connect to Github** button and follow the authorization process to your github account as below.


![CodeBuild Github Authorization](./images/codebuild-create-project-github-3.png "Codebuild Github Authorization")

![CodeBuild Github Authorization](./images/codebuild-create-project-github-4.png "Codebuild Github Authorization")

Now the **Source** section will have changed, allowing us to select our `CFNGoat` repository from github, you'll be able to scroll through a list of your Github repositories to find it:

![CodeBuild Github Connected](./images/codebuild-create-project-github-5.png "CodeBuild Github Connected")

![CodeBuild Github Authorization](./images/codebuild-create-project-github-6.png "CodeBuild Select Github Repository")

Under **Environment Image**, select **Managed Image**. Then select **Ubuntu**, **standard**, the latest numbered image (*aws/codebuild/standard:4.0 at the time of writing*) and select **always use the latest** from **image version**. Finally, set environment type to **Linux** if not already set, your setup should mirror the image below.

![CodeBuild Environment Details](./images/codebuild-create-project-github-11.png "CodeBuild Environment Details")

### Adding our Buildspec from the Bridgecrew Dashboard

Next comes the build spec. Select **Insert Commands**, then click **Switch to Editor** and paste the YAML code you copied from the Bridgecrew Dashboard earlier. Overwrite the previous contents completely.


![CodeBuild Buildspec Details](./images/codebuild-create-project-github-8.png "CodeBuild Buildspec Details")


![CodeBuild Buildspec Details](./images/codebuild-create-project-github-9.png "CodeBuild Buildspec Details")

**We've Completed our CodeBuild project setup!** Select **Create Build Project** to finalize!

![CodeBuild Create Project ](./images/codebuild-create-project-github-10.png "CodeBuild Create Project ")