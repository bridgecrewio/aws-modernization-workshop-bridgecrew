---
title: "AWS CodeBuild setup"
chapter: true
weight: 203
pre: "<b>5.2 </b>"
---

## Setting up AWS CodeBuild for our CloudFormation repository.
AWS CodeBuild paired with AWS CodePipeline is a CI/CD platform that can build projects, run jobs, and deploy infrastructure. We’re going to use it to scan the CloudFormation templates before deployment, allowing us to fail the build job and halt a deployment if there are any security violations in our CloudFormation code.

![AWS CodeBuild](./images/aws-codebuild-home.png "AWS CodeBuild")

We’ll also automatically send the results to Brigecrew to maintain a view across all of our infrastructure projects and share visibility throughout our organization.

First, tell the Bridgecrew dashboard you’re going to integrate AWS CodeBuild. To do this, open the integrations menu in your Bridgecrew account, select the `ADD INTEGRATION` button to open the integrations calalog.

![Bridgecrew Integrations Catalog](./images/bridgecrew-dash-integrations-catalog.png "Bridgecrew Integrations Catalog")

Select AWS CodeBuild from the catalog, to be guided through the integration setup:

![Bridgecrew CodeBuild Integration](./images/bridgecrew-dash-add-codebuild.png "Bridgecrew CodeBuild Integration")

You will be prompted to create a new Bridgecrew API key, this allows codebuild to talk to the Bridgecrew platform, name the key `Code Build Init Key` and click next, you will then be presented with the new API key, we need to save this for later. Create a new text file and save it.

![Bridgecrew CodeBuild Integration](./images/bridgecrew-dash-codebuild-api-key-integration.png "Bridgecrew CodeBuild Integration")

The next page provides a command to automatically add the API key to our AWS environment.

Run the command provided with your local aws CLI. This will save the Bridgecrew API key into your AWS System Manager’s parameter store so we can access it from our CodeBuild jobs later.

{{% notice info %}}
<p style='text-align: left;'>
If the aws command fails, your IAM user may not have the correct permissions to create parameters in AWS Systems Manager (SSM). In that case, you’ll need to add write permissions to the user.
</p>
{{% /notice %}}

Finally, we tell Bridgecrew about our CodeBuild environment, what git repository, branch, etc it's going to be responsible for running. This allows us to easily find the information reported back into Bridgecrew from CodeBuild.

![Bridgecrew CodeBuild Integration](./images/bridgecrew-dash-integrate-codebuild-attributes.png "Bridgecrew CodeBuild Integration")

We will be setting up codebuild on our fork of `CFNGoat`, so the `Repository Owner` will be your github user, `Repository Name` will be `cfngoat` and lets use the `master` branch by default.


Next, copy the `buildspec.yaml` configuration to keep handy for configuring our CodeBuild pipeline.


![Bridgecrew CodeBuild Integration](./images/bridgecrew-dash-codebuild-integration-save.png "Bridgecrew CodeBuild Integration")

### New Codebuild Project

Now go to your [AWS CodeBuild service](https://aws.amazon.com/codebuild/) select Create a Build Project and name your project `bridgecrew-tutorial`. 

![New CodeBuild Project](./images/codebuild-create-project-github-1.png "New CodeBuild Project")


Under the Source section, choose **GitHub** in the **Source Provider** dropdown and select **Connect using OAuth**. When you select Connect to GitHub, you’ll be prompted to authorize your GitHub account:

![CodeBuild Github Authorization](./images/codebuild-create-project-github-3.png "Codebuild Github Authorization")

![CodeBuild Github Authorization](./images/codebuild-create-project-github-4.png "Codebuild Github Authorization")

Now the **Source** section will have changed, allowing us to search for and select our `CfnGoat` repository from GitHub:

![CodeBuild Github Connected](./images/codebuild-create-project-github-5.png "CodeBuild Github Connected")

![CodeBuild Github Authorization](./images/codebuild-create-project-github-6.png "CodeBuild Select Github Repository")

Configure your Environment setup to mirror the image below:

![CodeBuild Environment Details](./images/codebuild-create-project-github-11.png "CodeBuild Environment Details")

### Adding our Buildspec 

To complete our build setup, we need to add the build commands. Select **Insert build commands**, and use the editor to overwrite the contents with the YAML code you copied from Bridgecrew earlier. 

![CodeBuild Buildspec Details](./images/codebuild-create-project-github-8.png "CodeBuild Buildspec Details")

![CodeBuild Buildspec Details](./images/codebuild-create-project-github-9.png "CodeBuild Buildspec Details")

Select **Create build project** to finalize our CodeBuild project setup!

![CodeBuild Create Project ](./images/codebuild-create-project-github-10.png "CodeBuild Create Project ")

