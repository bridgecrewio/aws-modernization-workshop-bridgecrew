---
title: "Account Setup"
chapter: false
weight: 6
pre: "<b>2.3 </b>"
---

## A free Bridgecrew account

The Bridgecrew platform will give us visibility, solutions and alerts from the first line of Kubernetes manifest all the waythrough to checking the running cluster’s security posture. Sign up or log in to an existing account at [https://bridgecrew.cloud](https://bridgecrew.cloud)


![alt_text](images/bcSignup.png "image_tooltip")


### Generate a Bridgecrew API key

Throughout this tutorial, you’ll need to use the Bridgecrew API token. You can [access it here](https://www.bridgecrew.cloud/login/signin?return_to=%2Fintegrations%2Fapi-token) or in your Bridgecrew account by navigating to the Integrations tab and selecting API Token. Add a token for the workshop and save it in your notes for later use. 


![alt_text](images/bcApiKey.png "image_tooltip")

## A free GitHub account

You will need a GitHub account to fork and edit our example infrastructure as code (IaC) so that you can automate and fix any Kubernetes issues!

Github discourages individuals from having more than one account. If you already have a Github.com account you canwill be able to follow along with this workshop using it, without worrying aboutissue or conflict with your private repositories.

![alt_text](images/gitHubLogin.png "image_tooltip")

### Fork KustomizeGgoat

This workshop uses our vulnerable-by-design Kubernetes & Kustomize project, [KustomizeGoat.](https://github.com/bridgecrewio/kustomizegoat/www.github.com/bridgecrewio/terragoat), This project givesgiving us a base set of deployments we can explore, edit, and remediate without needing to integratethe added friction of integrating your own code.


#### Fork the KustomizeGgoat repository on GitHub

To set up your demo environment, we’re going to fork the KustomizeGoat repository.

Head over to the [KustomizeGoat](https://github.com/bridgecrewio/kustomizegoat/www.github.com/bridgecrewio/terragoat) repository and fork it using the button in the upper right corner.


![alt_text](images/kustomizeGoatFork.png "image_tooltip")


If you have multiple organizations, GitHub will ask which of your orgs to fork into. Choose your personal account by selecting your GgitHhub username fromin the list. This will fork the repo.


Note down the URL for this new copy of the repository, also known as the “git clone address”, selectclick “code” and copy the `HTTPS` address that is shown., The `HTTPS` address format isit will be in the format:

```
https://github.com/<your-github-user>/kustomizegoat.git
```


![alt_text](images/kustomizeGoatClone.png "image_tooltip")
