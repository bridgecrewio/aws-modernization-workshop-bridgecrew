---
title: "Integrate Bridgecrew with GitHub"
chapter: false
weight: 15
pre: "<b>4.1 </b>"
---


## Integrate Bridgecrew with GitHub

To enable automated PR scanning on your repositories, goto the **Integrations **page at the bottom of the icon bar on the left.

Then, select **New Integration** and select **GitHub** from the **Code Repositories** options


![alt_text](./images/bcDashIntegrations.png "image_tooltip")


A pop-up dialog box will allow you to Authorize with your GitHub account and choose the repositories you want Bridgecrew to scan. Select **Authorize **to be redirected to GitHub to complete this step.


![alt_text](images/gitHubIntegrationConfigureAccount.png "image_tooltip")


If you have access to multiple GitHub organizations, you’ll be asked to select the one you wish Bridgecrew to access. You can select only specific repositories, or allow Bridgecrew to access all your repositories.


![alt_text](images/gitHubAuthorizeBridgecrew.png "image_tooltip")


You’ll then be redirected back to the Bridgecrew interface, where you will have the option to permit access to select specific subsets of repositories if needed.

 
![alt_text](images/bridgecrewActivateRepoScanning.png "image_tooltip")


Bridgecrew is now configured! Now Bridgecrew can scan your Git repositories for infrastructure as code issues and can automatically scan pull requests into your repositories for potential issues. 



### Check PR tagging settings  


Next, navigate to your username in the bottom left corner of the Bridgecrew Dashboard. Select `Code Repository Settings`.

 
Here you will find a section called `Code Reviews` and `Pull Request Bot Comments`. Make sure both options are on in order to have Pull Requests automatically scanned and annotated. While you're here, you can also select a specific issue severity at a global level here for annotated PRs. 


![alt_text](images/bridgecrewPullRequestBotComments.png "image_tooltip")