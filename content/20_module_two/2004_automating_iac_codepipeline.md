---
title: "AWS CodePipeline Setup"
chapter: true
weight: 24
pre: "<b>5.4 </b>"
---

## Setting up AWS CodePipeline to automatically trigger scans
To trigger CodeBuild to run the scan automatically on each new commit in your CfnGoat GitHub repository, we’ll need to configure AWS CodePipeline. You can skip this step, but if you do, you’ll only be able to run manual scans from the CodeBuild UI, AWS CLI, or APIs, which doesn’t provide the DevSecOps automation we’re looking for!


To set it up, go to [AWS CodePipeline](https://console.aws.amazon.com/codesuite/codepipeline/) and select **Create Pipeline**:

![AWS CodePipeline](./images/codepipeline-create-project-github-1.png "AWS CodePipeline")

After giving the pipeline a name, select **Next** and choose **Github (Version 2)** as the **source provider**.

![AWS CodePipeline Setup](./images/codepipeline-create-project-github-2.png "AWS CodePipeline Setup")

![AWS CodePipeline Setup](./images/codepipeline-create-project-github-3.png "AWS CodePipeline Setup")

As CodeBuild and CodePipeline are different tools, you'll also need to authorize CodePipeline to your GitHub account, select **Connect to Github** and follow the authorization redirects in the popup window.

Give the Github Connection a name:

![AWS CodePipeline Github Connection](./images/codepipeline-create-project-github-4.png "AWS CodePipeline Github Connection")

![AWS CodePipeline Github Authorize](./images/codepipeline-create-project-github-5.png "AWS CodePipeline Github Authorize")

Select which Github Repositories you want CodePipeline to receive events for, in this case, i've just selected the `CfnGoat` repository.

![AWS CodePipeline Github Authorize](./images/codepipeline-create-project-github-6.png "AWS CodePipeline Github Authorize")
![AWS CodePipeline Github Authorize](./images/codepipeline-create-project-github-7.png "AWS CodePipeline Github Authorize")

Once you’ve authorized GitHub, select **Install a new app** to finalize the GitHub integration and select **Connect**:

![AWS CodePipeline Github Authorize](./images/codepipeline-create-project-github-8.png "AWS CodePipeline Github Authorize")

The CodePipeline screen should refresh with a green **Sucessfully connected to GitHub** message:

![AWS CodePipeline Github connected OK](./images/codepipeline-create-project-github-9.png "AWS CodePipeline Github connected OK")

Now that CodePipeline has access to our GitHub repository, we can select it as the pipeline source. Select the **master** (or **main** branch) to have our pipeline run when commits to this branch occur:

![AWS CodePipeline Select Repo](./images/codepipeline-create-project-github-10.png "AWS CodePipeline Select Repo")

## Instruct CodePipeline to trigger our CodeBuild

When CodePipeline sees a new commit in our GitHub repository, it will trigger a build action. To set this to be our CodeBuild commands, select the same region as the CodeBuild project, then select the CodeBuild project, **bridgecrew-tutorial**.

Leave the default of **Single Build** selected and select **Next**

![AWS CodePipeline Select Repo](./images/codepipeline-create-project-github-11.png "AWS CodePipeline Select Repo")

On the next screen, select **Skip deploy stage**. We don’t want to deploy our CfnGoat CloudFormation to AWS as we’re just highlighting how to stop a build from progressing if there are security violations!

![AWS CodePipeline Select Repo](./images/codepipeline-create-project-github-12.png "AWS CodePipeline Select Repo")

Finally, select **Create pipeline** on the review page, which will trigger your new CodePipeline to immediately run against the latest commit in our CfnGoat repository:

![AWS CodePipeline Select Repo](./images/codepipeline-create-project-github-13.png "AWS CodePipeline Select Repo")

**Now we don’t need to manually run the Bridgecrew CLI; your developers will get a Bridgecrew scan every time they commit!** 
