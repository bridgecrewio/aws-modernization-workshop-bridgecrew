---
title: "Create A pull request"
chapter: false
weight: 16
pre: "<b>4.2 </b>"
---


### Create infrastructure with a pull request

To see our new security controls in action, let's create a pull request to modify our development environment configuration!

![alt_text](images/kustomizeGoatGHRepo.png "image_tooltip")


In GitHub, on your fork of **KustomizeGoat**, navigate into the **kustomize** > **overlays** and **dev** directories: 



![alt_text](images/gitHubEditThisFile2.png "image_tooltip")


Select on the **kustomization.yaml** file to open it in the GitHub web viewer, and select edit.

![alt_text](images/gitHubEditThisFile.png "image_tooltip")

Let's make a simple change right now to trigger a build. Modify the name of the dev namespace.


![alt_text](images/githubEditFile.png "image_tooltip")


Make sure to you select *Create a new branch for this commit* and propose the change.

![alt_text](images/githubCommitNewPatchBranch.png "image_tooltip")


This will automatically queue up a new pull request with your change included, on the next page, select *Create Pull Request*

![alt_text](images/githubRaisePR.png "image_tooltip")

The pull request will load, and you will immediately see Bridgecrew checks ready to scan the proposed infrastructure changes. \

![alt_text](images/prScanning.png "image_tooltip")


