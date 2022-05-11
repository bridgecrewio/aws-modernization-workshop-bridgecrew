---
title: "Bridgecrew Code Reviews"
chapter: false
weight: 11
pre: "<b>3.2 </b>"
---

Each time ArgoCD tries to deploy our development environment to the Kubernetes cluster, the cluster is instructed to check the security posture of incoming Kubernetes manifests with the Bridgecrew admission controller. 

Details of all the issues found with the development deployment can be seen in this view, with filters for severity, tags, and other important attributes.

![alt_text](images/bcDashFullScreenshot.png "image_tooltip")

We’ve detected 17 issues on our Deployment object and no issues on the service object.  This explains why the service object was successfully deployed to the Kubernetes cluster, but the Deployment was not.

![alt_text](images/bcDashProjects.png "image_tooltip")

At the bottom of each flagged item, we’ll see more information aboutthe security issue that prevented a successful deployment to the cluster. 


![alt_text](images/bridgecrewDashExampleIssue.png "image_tooltip")


In this example, one issue we see is that we have no securityContext settings on our pods or containers within the Deployment.


![alt_text](images/bcDashGuidelineInfo.png "image_tooltip")


We can bring up more information and guidance on the issue with the lightbulb symbol on the issue’s header.

Guidelines (like [this page](https://docs.bridgecrew.io/docs/bc_k8s_28)) provide more detail and context for each issue. 
 

![alt_text](images/bcGuidelines.png "image_tooltip")

