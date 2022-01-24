---
title: "Pull request fixes"
chapter: false
weight: 302
pre: "<b>6.2 </b>"
---

## Automating fixes through pull requests

Now that you’ve pulled in multiple infrastructure sources, you may get overwhelmed at the prospect of fixing the several dozen issues Bridgecrew has identified. To help us implement fixes as fast as possible, Bridgecrew generates and pushes fix pull requests back into your GitHub repository. These fixes are sourced from static recommendations and Smart Fixes that are fixes sourced from your own repositories based on other code that has passed those checks.

Let’s walk through the process with one of the policies you looked at earlier, "Ensure secure transfer required is enabled."

![Bridgecrew Projects page](images/bridgecrew_projects_page.png "Bridgecrew Projects page")

The lightbulb icon takes you to the Bridgecrew docs for more information about the violation. We can also suppress that check for this specific resource. Finally, in the middle is the **Fix** button. This enables you to automatically create a pull request with the diff shown. In this case, it will remove the acl with `public-read` access and `force_destroy` setting.

That's a static fix. Next, look for the "Ensure Azure SQL server send alerts to field value is set" violation. There is no one right answer for every company for who should be the contact, but based on other code in my repo, `securityengineer@bridgecrew.io` is the input I've used every time in the past. That's a lot easier than looking it up.

![Smart Fix](images/smart_fix.png "Smart Fix")

You can include other fixes, but for the sake of this workshop, we’ll just do the two. Select **Submit**.

That created a pull request, but you’ll need to approve the patch to make the changes in your repository. Over in your TerraGoat repository in GitHub, you’ll see a new PR under the “Pull requests” tab, which is ready for review:

![GitHub with a Code Review](images/github_code_review.png "GitHub with a Code Review")

Because of the scans from previous steps, the Merge button won’t be highlighted. Merge the patch anyway. You’ll receive a confirmation that the PR was merged and closed.

![Successful PR](images/github_pr_success.png "Successful PR")

Make sure to pull the origin locally to update your local copy of TerraGoat with the patch.

**Congratulations!**

You’ve built an automated IaC scanning workflow in a live environment and automated the fixing of an IaC template!