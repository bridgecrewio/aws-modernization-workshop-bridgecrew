---
title: "Create A Pull Request"
chapter: false
weight: 16
pre: "<b>4.2 </b>"
---


### Creating Infrastructure with a Pull Request!

To see our new security controls in action, let's create a pull request to modify our Dev environment configuration!

![alt_text](images/kustomizeGoatGHRepo.png "image_tooltip")


In GitHub, on your fork of **KustomizeGoat**, click into the **kustomize** > **overlays** and **dev** directories: 



![alt_text](images/gitHubEditThisFile2.png "image_tooltip")


Click on the **kustomization.yaml** file to open it in the GitHub web viewer, and click edit

![alt_text](images/gitHubEditThisFile.png "image_tooltip")

Lets make a simple change right now, and modify the name of the dev Namespace


![alt_text](images/githubEditFile.png "image_tooltip")


Ensure you select *Create a new branch for this commit* and propose the change.

![alt_text](images/githubCommitNewPatchBranch.png "image_tooltip")


This will automatically queue up a new pull request with your change included, on the next page, press *Create Pull Request*

![alt_text](images/githubRaisePR.png "image_tooltip")

The pull request will load, and you will immediately see Bridgecrew checks about to run against the proposed infrastructure changes. \

![alt_text](images/prScanning.png "image_tooltip")


