---
title: "IDE Integration"
chapter: false
weight: 18
pre: "<b>5 </b>"
---


## The new scenario 

![alt_text](images/weAreHere-m4-1.png "image_tooltip")


Not only do we now have controls blocking severe security issues from our Kubernetes cluster, but we also have early warning systems directly in the developers eye-line (Pull Request scans and CI testing).

But we’re still causing a little bit of friction! no-one likes thinking they are finished, committed, pull request raised, only to need to go back and make more changes.

Here we’ll add the VSCode IDE plugin, to surface potential issues right at the point of development!


## Fixing before commit

The best issue is one that never even makes it into a git commit, and by highlighting potential issues in VSCode, we can achieve just that!

For this section, we’ve jumped out of our pre-built environment, and I have cloned by KustomizeGoat fork directly onto my local machine in order to open within VSCode!

By all means skip this section if you’d rather not touch your local machine setup, the rest of the workshop does not depend on this VSCode module. (It is very cool though!)

Here we can see VSCode, with the *Extensions* sidebar open on the left, we have found and installed the *Checkov by Bridgecrew* extension.


![alt_text](images/vsCodePlugin.png "image_tooltip")


The extension simply needs a Bridgecrew API key to function, like the one we created with the GitHub action integration, and can be entered by clicking on the new *checkov* status item on the blue bar at the bottom of the VSCode window:


![alt_text](images/vsCodeCheckovBar.png "image_tooltip")


Checkov is currently scanning the `kustomize/base/deployment.yaml` file within our KustomizeGoat repository, it will scan any IaC (infrastructure as code) file when opened in VSCode.

 
Once the scan is complete, any issues found will be annotated onto the Kubernetes objects themselves with red underline of the object in question. 


![alt_text](images/vsCodeSqiggle.png "image_tooltip")


 
Hovering over the red underlined object will provide more context, and a list of all the same issues that we were seeing in our CI/CD pipeline and Pull Requests! 


 

![alt_text](images/vsCodeProblemList.png "image_tooltip")


There are other ways to surface this information rather than the hover-over dialog box, opening the VSCode *Problem* payne will allow you to see Checkov’s findings detached from the code display.


![alt_text](images/vsCodeProblemsBottom.png "image_tooltip")

![alt_text](images/vsCodeAnnotationStyle2.png "image_tooltip")



## Kubernetes mode vs Kustomize mode

In VSCode, kubernetes objects are scanned and annotated as they are found, it makes no sense to render a resulting kustomize manifest at this stage (it may not even be complete), so any valid Kubernetes objects, per-file, will be scanned as-is.

Therefore results could vary slightly from VSCode and the fully rendered Kustomize environments in CI/CD and our Admission Controller checks; however having the same policies being enforced in all these locations aims to help the developer experience when it comes to implementing DevSecOps and a more secure IaC posture.


## Congrats, That's all for IDE enablement!

 
At the time of this workshop, we also support *IntelliJ* with the same style of plugin! Check it out if interested from the *Integrations* page in *Bridgecrew*.
