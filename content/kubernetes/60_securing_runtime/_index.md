---
title: "Securing Runtime"
chapter: false
weight: 19
pre: "<b>6 </b>"
---


## The new scenario 

![alt_text](images/weAreHere-m4-1.png "image_tooltip")


Awesome work! Now we have helpful security feedback in VSCode, security warnings in pull requests, guradrails for CI/CD on our main branch, and the admission controller providing backup for the most critical issues.
 
We’ve shifted left and have most of our lifecycle covered, but we never considered where our deployments are going–runtime.

Sonsider the following security concerns:

* Anything deployed before every team implements a DevSecOps pipeline, with fewer security checks and balances enforced.
* Operator error causing a change an IAM policy when they debug an issue in production.
* An attacker may already have a foothold in our system, which would allow them to edit anything they have permission to access in an attempt to broaden their privileges.

Considering these potential security issues, our AWS accounts are likely to have misconfigurations. This means we now need to ensure that we also hold our runtime environment to the same expectations as we’re now holding our infrastructure as code.


## The many faces of runtime

If our infrastructure was deployed using another infrastructure as code framework where the IaC directly created AWS objects, such as Terraform or CloudFormation, we would only need to monitor the AWS account itself.  Bridgecrew can use the AWS API’s to do this via the AWS Runtime integration we’ll enable later.

Our workloads that run in AWS have an added layer of abstraction with Kubernetes, and Kubernetes brings its own context and APIs. 

Because workloads are often not siloed and typically have supporting services like storage, databases, queues, and IAM, we will need to enable the AWS Integration and Kubernetes Runtime integration to have complete visibility into our runtime environment.