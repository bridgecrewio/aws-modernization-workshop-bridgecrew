---
title: "ArgoCD"
chapter: false
weight: 10
pre: "<b>3.1 </b>"
---

In order to access the ArgoCD web interface within our Kubernetes cluster, we'll need to know the public IP address of our workshop environment.

Clicking the link below, will load the CloudFormation *stacks* page. Select `bridgecrew-workshop` and select the *Outputs* tab, where we will see the public IP and ArgoCD URL.

[https://us-east-2.console.aws.amazon.com/cloudformation/home?region=us-east-2#/stacks?filteringStatus=active&filteringText=&viewNested=true&hideStacks=false](https://us-east-2.console.aws.amazon.com/cloudformation/home?region=us-east-2#/stacks?filteringStatus=active&filteringText=&viewNested=true&hideStacks=false)

The URL will be in the form `https://<CLUSTER IP>:32443` click this link and you will be  prompted with the ArgoCD login screen. 

You can `cat .bcworkshop/.argo-password` within our Cloud9 terminal to reveal the password for login. The username is `admin`.

 
![alt_text](images/argoCdLogin.png "image_tooltip")


Log into the ArgoCD web interface to see the current state of our environment.


![alt_text](images/argoCdDash.png "image_tooltip")


We can see that one of our environments, `kustomizegoat-prod` is healthy, it is “synced” between what we’ve declared in our infrastructure-as-code configuration, and what is running on our cluster.  

Lets take a look at the healthy prod environment in this visual manor, rather than digging through the kubernetes manifests for now.

Click anywhere on the “kustomizegoat-prod” box for a deeper look.


### kustomizegoat-prod


![alt_text](images/argoSuccessfulDeployment.png "image_tooltip")


In this view, we can see a pretty simple deployment, a Kubernetes deployment, with a single ReplicaSet, running two Pods. Then a Service loadbalancer linking to the pods, great!

Now we’ll do the same with the dev environment to see what is going on there!


### kustomizegoat-dev


![alt_text](images/argoProcessing.png "image_tooltip")


In dev, we see a different story, the service loadbalancer is created, but the Deployment has no children, no ReplicaSet and no Pods, we also see an error in the ArgoCD interface:


![alt_text](images/argoDevEnvError.png "image_tooltip")

 Clicking on the “App Conditions: 1 Error” message, we see why this deployment hasn’t been successful.


![alt_text](images/argoErrorAdmissionController.png "image_tooltip")

It looks like the deployment was blocked from running on the cluster due to a number of security issues found by Bridgecrew’s Kubernetes admission controller, which the dev team had just installed. But thats not the nicest way to view the error. 
 
Follow the `complete details` link at the bottom of the error message for a clearer view.
