---
title: "Setup AWS CodePipeline"
chapter: true
weight: 24
---

## Setting up CodePipeline to automatically trigger scans
If you want CodeBuild to run the scan automatically on each new commit in your CFNGoat Github repository, you’ll need to configure AWS CodePipeline. You can skip this step, but if you do, you’ll only be able to run manual scans from the CodeBuild UI, AWS CLI, or API's, which doesn't provide us the **DevSecOps** automation we're looking for!

To set it up, go to [AWS CodePipeline](https://console.aws.amazon.com/codesuite/codepipeline/) and select **Create Pipeline**:

![AWS CodePipeline](./images/codepipeline-create-project-github-1.png "AWS CodePipeline")

After giving the pipeline a name, select Next and choose **Github (Version 2)** as a source provider.

![AWS CodePipeline Setup](./images/codepipeline-create-project-github-2.png "AWS CodePipeline Setup")
![AWS CodePipeline Setup](./images/codepipeline-create-project-github-3.png "AWS CodePipeline Setup")

As CodeBuild and CodePipeline are different tools, we'll also need to authorize CodePipeline to your GitHub account, select **Connect to Github** and follow the authorization redirects in the popup window.

Give the Github Connection a name:

![AWS CodePipeline Github Connection](./images/codepipeline-create-project-github-4.png "AWS CodePipeline Github Connection")

![AWS CodePipeline Github Authorize](./images/codepipeline-create-project-github-5.png "AWS CodePipeline Github Authorize")

Select which Github Repositories you want CodePipeline to receive events for, in this case, i've just selected the CFNGoat repository.

![AWS CodePipeline Github Authorize](./images/codepipeline-create-project-github-6.png "AWS CodePipeline Github Authorize")
![AWS CodePipeline Github Authorize](./images/codepipeline-create-project-github-7.png "AWS CodePipeline Github Authorize")

Click **Install a new app** to finalize the Github integration, then click **Connect**

![AWS CodePipeline Github Authorize](./images/codepipeline-create-project-github-8.png "AWS CodePipeline Github Authorize")

The CodePipeline screen should refresh with a green **Sucessfully connected to GitHub** message:

![AWS CodePipeline Github connected OK](./images/codepipeline-create-project-github-9.png "AWS CodePipeline Github connected OK")

Now CodePipeline has access to our github repo, we can select it as the pipeline source, as below, we also select the **master** (or **main** branch), to have our pipeline run when commits to this branch occur.

![AWS CodePipeline Select Repo](./images/codepipeline-create-project-github-10.png "AWS CodePipeline Select Repo")

## Instruct CodePipeline to trigger our CodeBuild

When CodePipeline see's a new commit in our Github repository, it will trigger a build action, in our case, we want this to be our CodeBuild setup, select the **same region** as the CodeBuild project, then select the CodeBuild project name, **bridgecrew-tutorial**.

Leave the default of **Single Build** selected and select

![AWS CodePipeline Select Repo](./images/codepipeline-create-project-github-11.png "AWS CodePipeline Select Repo")

Click **Next** then **Skip Deploy Stage** on the next screen, we don't want to deploy our CFNGoat CloudFormation to AWS as we're just highlighting howto stop a build progressing if there are Security Violations! 

![AWS CodePipeline Select Repo](./images/codepipeline-create-project-github-12.png "AWS CodePipeline Select Repo")

Finally, ** Create Pipeline ** on the review page:

![AWS CodePipeline Select Repo](./images/codepipeline-create-project-github-13.png "AWS CodePipeline Select Repo")

The Pipeline will immediatley run! **Hit next to explore our new automated CI/CD Setup!**
