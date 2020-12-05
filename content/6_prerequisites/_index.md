---
title: "Prerequisites"
chapter: false
weight: 4
pre: "<b>3 </b>"
---

Before we get started, make sure you have the following prerequisites. To get the most out of this tutorial, it will also be helpful to have a basic understanding of git, AWS core concepts (IAM, regions, UI, CLI, APIs), and CI/CD principles.

### Git
```
git --version
```
If you don’t have git installed, [do so here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git/).

### GitHub account

If you don’t have a GitHub account, please [sign up for one here](https://github.com/join).


### AWS account

If you are at an AWS event where the AWS Event Engine is being used, [please click here.](./699_event_engine.html)

For this tutorial, you’ll need an AWS account and an IAM user that can make programmatic calls.

```bash
cat ~/.aws/credentials
[default]
aws_access_key_id = ABCDEFGHIJKLMNOPQRSTUVWXYZ1
aws_secret_access_key = awssecretkeystring
```

### AWS CLI

```bash
aws --version
```
You can test the current credentials configured for your local aws cli with the `aws sts get-caller-identity` command.


{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Bridgecrew and AWS services can be architected to build a solution while demonstrating best practices along the way. These examples, especially the intentionally vulnerable "CFNGoat" repository, are not intended for use in production environments.
</p>
{{% /notice %}}




