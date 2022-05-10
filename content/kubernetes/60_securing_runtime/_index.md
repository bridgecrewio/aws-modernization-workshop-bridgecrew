---
title: "Securing Runtime"
chapter: false
weight: 19
pre: "<b>6 </b>"
---


## The new scenario 

![alt_text](images/weAreHere-m4-1.png "image_tooltip")


Awesome work! Now we have helpful security feedback in VSCode, security warnings in Pull Requests, Blocking CI/CD on our main branch, and the admission controller providing backup for the most critical issues! 
 
We’ve shifted so far left and pretty much got our lifecycle covered, but we never considered where our deployments were going, “Runtime”.

Our AWS accounts are just as likely to have misconfigurations, consider the following possibilities:



* Anything deployed before all the companies teams’ implemented a DevSecOps pipeline, with less security checks and balances enforced.
* Operator error changing an IAM policy when debugging an issue in production.
* An attackers foothold, editing anything they have permission to access to try and broaden their privileges

Lets make sure we complete the circle by also holding our runtime environment to the same expectations as we’re now holding our infrastructure code!


## The many faces of runtime

If our infrastructure was deployed using another Infrastructure-as-code framework, such as Terraform, or CloudFormation, where the IaC was directly creating AWS objects, we would only need to monitor the AWS account itself; Bridgecrew can use the AWS API’s to do this via the AWS Runtime integration we’ll enable below.

However, our workloads, while running in AWS, are ontop of another layer of abstraction, Kubernetes, which brings it’s own context and API’s.

For full visibility of our runtime environment (as workloads are often not alone, with supporting services such as storage, databases, queues, not to mention IAM) we will need to enable AWS Integration *AND* Kubernetes Runtime integration to see the whole picture.

