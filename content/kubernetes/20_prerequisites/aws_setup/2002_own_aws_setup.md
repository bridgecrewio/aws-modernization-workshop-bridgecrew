---
title: "Own AWS environment"
chapter: false
weight: 5
pre: "<b>2.2.2 </b>"
---

{{% notice warning %}}
Disclaimer: We will be using an AWS account to show Bridgecrew’s runtime capabilities and drift detection. If you follow along, remember to shut down any AWS services to avoid additional fees.
{{% /notice %}}

## AWS environment setup

{{% notice info %}}
Your account must have the ability to create new IAM roles and scope other IAM permissions.
{{% /notice %}}

1. If you don't already have an AWS account with Administrator access: [create
one now by clicking here](https://aws.amazon.com/getting-started/)

1. Once you have an AWS account, ensure you are following the remaining workshop steps
as an IAM user with administrator access to the AWS account:
[Create a new IAM user to use for the workshop](https://console.aws.amazon.com/iam/home?#/users$new)

1. Enter the user details:
![Create User](/images/iam-1-create-user.png)

1. Attach the AdministratorAccess IAM Policy:
![Attach Policy](/images/iam-2-attach-policy.png)

1. Click to create the new user:
![Confirm User](/images/iam-3-create-user.png)

1. Take note of the login URL and save:
![Login URL](/images/iam-4-save-url.png)