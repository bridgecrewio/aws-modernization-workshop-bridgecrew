---
title: "Create our Scenario"
chapter: false
weight: 7
pre: "<b>2.4 </b>"
---


##  The Automated AWS Workshop Environment

Your workshop environment will drop you into an example development team, at the start of their journey through the DevSecOps world!

They already use ‘Infrastructure as Code’ to define their environments, and the deployment target is a Kubernetes cluster, which is also setup.

To pre-build this environment for each workshop attendee, we'll run some CloudFormation within our AWS account.

## An introduction to “KIND”

KIND, or “Kubernetes in Docker” is a simple way to createof creating local Kubernetes clusters for testing, experimentation and development.

[https://kind.sigs.k8s.io/](https://kind.sigs.k8s.io/)

![alt_text](images/kindLogo.png "image_tooltip")

As the name suggests, Kind nests a Kkubernetes cluster inside containers on your existing (Docker, Podman, ContainerD, etc) system. 

We’ll be using Kind to ensure everyone has the same, repeatable Kubernetes configuration for this workshop, regardless of deployment location.


### Setting up the workshop environment via CloudFormation

	
1. From within your AWS Account, go to the CloudFormation Service.
2. Use the following Amazon S3 URL as a template source: 
3. Provide a name for the stack. For example, “bridgecrew-k8s-workshop” would be fine.
4. Fill out the required parameters, these will help set up the environment without manual steps later in the workshop!

![alt_text](images/cfStackDetailsInputPrompt.png "image_tooltip")

Fill in your git clone address for your fork of [https://github.com/bridgecrewio/kustomizegoat](https://github.com/bridgecrewio/kustomizegoat) in the `KustomizeForkURL` field. 



![alt_text](images/cfKustomizeForkUrl.png "image_tooltip")


Enter your Bridgecrew API key fromfor your free Bbridgecrew account in the `UserBridgecrewAPI` field.


![alt_text](images/cfBridgecrewAPIToken.png "image_tooltip")

Enter any public SSH key you wish to use (for which you own the private key). Yyou will use this to log into the KIND machine. Paste this in full into the `UserSSHKey` field. 


![alt_text](images/cfUserSSHKey.png "image_tooltip")

Finally, enter *your own* current public IP address from wherever you are attending this workshop. We will lock down certain public service access to this IP for security. You can edit this later if needed. 

Add this IP into the ‘YourPublicIP’ field: 


![alt_text](images/cfPublicIP.png "image_tooltip")

5. Select “NEXT”. There are no further configuration options needed, `select the checkbox` to confirm IAM roles will be created through this automation, then select `Create stack` Click through to create the stack.


![alt_text](images/cfCreateStack.png "image_tooltip")


### VSCode


Not just for it’s code editing capabilities, we will also demonstrate security plugins for VSCode during this webinar. Security plugins for VSCode  which will helpaide your development teams to spot misconfigurations much earlier in the development process., To download VSCode for free, visit get yourself the latest copy for your environment of VSCode, for free, from [https://code.visualstudio.com/download.](https://code.visualstudio.com/download)

