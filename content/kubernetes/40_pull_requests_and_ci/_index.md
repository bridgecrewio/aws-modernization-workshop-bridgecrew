---
title: "Pull Requests and CI"
chapter: false
weight: 14
pre: "<b>4 </b>"
---


## The new scenario 

![alt_text](images/weAreHere-m4-1.png "image_tooltip")


So far, our development team is that happy we’ve blocked issues from reaching the cluster. Now let's work to make that feedback loop better. 
 
We already know our infrastructure as code is stored in a GitHub repository, and now it’s time to take a look at adding some extra layers of defense! 

## Pull requests as security gates

Following GitOps principles, our “production/main” branches of our Git repository should reflect exactly what is in production at any point in time. Changes should be reconciled so that the Kubernetes cluster (or any other runtime resource) reflects the changes in our Git “source of truth”.

Therefore, it’s important that changes to our main branches are made carefully and that developers have the ability to run tests on changes before they are considered for inclusion.

Just like with CD, automation is key here. If manual testing was required in this process, each small change would involve a significant amount of wasted time spent testing changes. Additionally, manual testing would introduce mistakes from human errors and would decrease team morale.

By integrating Bridgecrew directly with our GitHub repository, we can enable pull request scanning and automatic annotation of security issues within the Pull Request itself. This enables a simpler, more streamlined developer experience and keeps our security issues even further away from production.


![alt_text](images/weAreHere-m4-2.png "image_tooltip")
