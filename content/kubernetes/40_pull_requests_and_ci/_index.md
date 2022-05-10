---
title: "Pull Requests and CI"
chapter: false
weight: 14
pre: "<b>4 </b>"
---


## The new scenario 

![alt_text](images/weAreHere-m4-1.png "image_tooltip")


Our Dev team is happy we’ve blocked issues from reaching the cluster, but lets try and make that feedback loop better, and our errors more readable and easier to fix! 
 
We already know our infrastructure code is stored in a GitHub repository, it’s time to take a look at adding some extra layers of defense! 

## Pull requests as security gates

Following GitOps principals, our “production/main” branches of our git repository should reflect exactly what is in production at this point in time, changes should be reconciled so that the Kubernetes cluster (or any other runtime resource for that matter) reflects the changes in our Git “source of truth”.

It’s important then, that changes to our main branches are made carefully, with engineers given the abilities to run tests on changes before they are considered for inclusion!

Automation is key here, just as in Continuous Deployment, as otherwise each small change would carry a huge amount of wasted time in manual testing (which commonly leads to mistakes through human error or lack of team morale through dull repetitive tasks).

By integrating Bridgecrew directly with our GitHub repository, we can enable pull request scanning and automatic annotation of security issues in the Pull Request, providing a much earlier, cleaner developer experience and keeping our security issues even further away from Prod!


![alt_text](images/weAreHere-m4-2.png "image_tooltip")
