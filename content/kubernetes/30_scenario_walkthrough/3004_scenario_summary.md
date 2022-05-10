---
title: "Scenario Summary"
chapter: false
weight: 13
pre: "<b>3.4 </b>"
---

## You are here!

This is all well and good, there’s a free Admission controller that our Dev team have installed into our Kubernetes cluster to prevent bad things being deployed, however, lets look where in the development cycle this is currently happening: 


![alt_text](images/weAreHere.png "image_tooltip")



We’ve blocked this deployment in the red oval, a lot of developers time, commands, processing time on code testing, and other processes have already happened before this point. \

I’m sure we can make it easier for issues to be spotted earlier in the pipeline!



Plus, by the time we’re at the Kubernetes cluster, our alerts look like this:
![alt_text](images/bcAdmissionControllerBadUXFileName.png "image_tooltip")


That random filename is the internals of the Kubernetes admission controller rendering our template and checking it for errors, not very developer friendly as a security output! We’ve lost the context of the original code repository, let's see what else we can do to improve developer experience here!

