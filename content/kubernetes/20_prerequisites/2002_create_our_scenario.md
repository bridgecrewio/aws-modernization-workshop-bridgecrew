---
title: "Create our scenario"
chapter: false
weight: 7
pre: "<b>2.4 </b>"
---


##  The automated AWS workshop environment

To pre-build this environment for each workshop attendee, we'll run some CloudFormation within our AWS account.

## An introduction to “kind”

[kind](https://kind.sigs.k8s.io/), or “Kubernetes in Docker” is a simple way to create local Kubernetes clusters for testing, experimentation and development.

![alt_text](images/kindLogo.png "image_tooltip")

As the name suggests, kind nests a Kubernetes cluster inside containers on your existing (Docker, Podman, ContainerD, etc) system.

We’ll be using kind to ensure everyone has the same, repeatable Kubernetes configuration for this workshop, regardless of deployment location.

### Setting up the workshop environment via CloudFormation
	
1. Clicking the following link will open CloudFormation and pre-fill the template source from Amazon S3: [https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2&skipRegion=false#/stacks/create/review?templateURL=https://kubernetes-workshop-cloudformation.s3.us-east-2.amazonaws.com/workshop-init-cloudformation.yaml&stackName=bridgecrew-workshop](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2&skipRegion=false#/stacks/create/review?templateURL=https://kubernetes-workshop-cloudformation.s3.us-east-2.amazonaws.com/workshop-init-cloudformation.yaml&stackName=bridgecrew-workshop)

2. Fill out the required parameters described below. these will enable CloudFormation to set up the environment without manual steps later in the workshop!

![alt_text](images/cfStackDetailsInputPrompt.png "image_tooltip")

Fill in your git clone address for your fork of [https://github.com/bridgecrewio/kustomizegoat](https://github.com/bridgecrewio/kustomizegoat) in the `KustomizeForkURL` field. 



![alt_text](images/cfKustomizeForkUrl.png "image_tooltip")


Enter your Bridgecrew API key from your free Bridgecrew account in the `UserBridgecrewAPI` field.


![alt_text](images/cfBridgecrewAPIToken.png "image_tooltip")


Finally, enter your current [public IP address](http://whatismyip.com/) from wherever you are attending this workshop. We will lock down certain public service access to this IP for security. You can edit this later if needed.

Add this IP into the ‘YourPublicIP’ field: 


![alt_text](images/cfPublicIP.png "image_tooltip")

5\. Select “NEXT”. There are no further configuration options needed, `select the checkbox` to confirm IAM roles will be created through this automation, then select `Create stack` Click through to create the stack.


![alt_text](images/cfCreateStack.png "image_tooltip")

#### Verify Cloud9 environment access

Finally, lets check on the environment that CloudFormation has built for us. 
Click here: [https://us-west-2.console.aws.amazon.com/cloud9/home/shared?region=us-west-2](https://us-west-2.console.aws.amazon.com/cloud9/home/shared?region=us-west-2) to load the *Cloud9 Environments* within your AWS account. You will see a single `bridgecrew-workshop` environment which our automation has created!

Click *Open IDE*. You will be taken to an environment which we will use for the rest of the workshop.

* The file browser down the left hand side already has your fork of KustomizeGoat available.
* The terminal window along the bottom of the browser tab is within our kubernetes cluster, `kubectl`, `checkov` and other commands needed for the workshop will work out of the box.
* You can open/edit files by double clicking on a file within the file browser from the left, just like a locally installed IDE.

If you have any issues accessing this environment, let your workshop host know.
