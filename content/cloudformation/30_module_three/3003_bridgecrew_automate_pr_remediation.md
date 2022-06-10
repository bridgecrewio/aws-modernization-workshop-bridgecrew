---
title: "Pull request fixes"
chapter: true
weight: 303
pre: "<b>6.3 </b>"
---

## Automating fixes through pull requests

Now that you’ve pulled in multiple infrastructure sources, you might be getting overwhelmed at the prospect of fixing the several dozen issues Bridgecrew has identified. To help you implement fixes as fast as possible, Bridgecrew generates and pushes fix pull requests back into your GitHub repository. 

Let’s walk through the process with one of the policies we looked at earlier, **Ensure S3 bucket has ‘restrict_public_bucket’ enabled**:


![Projects page](./images/dash-remediate-1.png "Projects page")


You can see that this issue has a suggested fix available (green for new lines added). We can click on the lightbulb icon and follow the "View Guidelines" link to see the docs for that misconfiguration.


![Git remediation workflow](./images/dash-remediate-2.png "Git remediation workflow")

Let's open a pull request. Select the **FIX** button then **Submit** in the upper right corner.

![Git remediation workflow](./images/dash-remediate-3.png "Git remediation workflow")

The remediation modal shows there will be a pull request fix raised against your GitHub repository.

![Git remediation workflow](./images/dash-remediate-4.png "Git remediation workflow")


After you select **Submit**, you’ll see a message confirming the pull request has been successfully raised with a link to the PR in GitHub. You’ll also see the remediation has had the effect of hiding the issue from the Projects list; other policy violations are listed, but the one we addressed is gone.

You’ll also notice, however, that the issue is still present from our CodePipeline source, so we’re not secure yet!

Over in our CfnGoat repository in GitHub, we’ll see a new PR under the Pull requests tab, which is ready for review:

![Git remediation workflow](./images/dash-remediate-6.png "Git remediation workflow")


![Git remediation workflow](./images/dash-remediate-7.png "Git remediation workflow")

Digging into the changed files, you’ll see the updated code that will soon be merged.


![Git remediation workflow](./images/dash-remediate-8.png "Git remediation workflow")


### Bringing it all together.

Merging our pull request in GitHub triggers our CI/CD deployment in AWS CodePipeline that we previously set up.

You may be able to tell where this is going!

![Git remediation workflow](./images/dash-remediate-9.png "Git remediation workflow")

Notice our merged pull request commit has triggered the build:

![Git remediation workflow](./images/dash-remediate-10.png "Git remediation workflow")
![Git remediation workflow](./images/dash-remediate-11.png "Git remediation workflow")

Of course, the scan will still fail as there are several other security issues affecting the CfnGoat repository, but if we head back to Bridgecrew, the issue we just fixed is gone:

![Git remediation workflow](./images/dash-remediate-12.png "Git remediation workflow")

Now we know that the issue is not only fixed at source, but also that the fix has also made it through the CI/CD pipeline into production!

#### Congratulations!
You’ve built an automated IaC scanning workflow in a live environment and automated the fixing of an exposed S3 bucket! 
