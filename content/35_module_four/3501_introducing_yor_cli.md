---
title: "Tag & Trace resources"
chapter: true
weight: 351
pre: "<b>7.1 </b>"
---

## Using the Yor CLI

We're going to use the Yor CLI to add tracability tags to our CFNGoat CloudFormation infrastructure.

## Installing Yor

We have already installed Yor into our Cloud9 environment at the beginning of this workshop, for other installation options (for example, to use Yor locally on your machine, see the options in the [Yor.io installation docs](https://yor.io/2.Using%20Yor/installation.html)

## Run yor to tag CFNGoat

Simply run the following command within the `cfngoat` directory for Yor to tag all of our CloudFormation with useful tags

```bash
yor tag -d .
```

You can run a `yor list-tags` to find out which tags will be added by default:

```bash
➜  cfngoat git:(master) ✗ yor list-tags
+------------+----------------------+--------------------------------+
|   GROUP    |       TAG KEY        |          DESCRIPTION           |
+------------+----------------------+--------------------------------+
| code2cloud | yor_trace            | A UUID tag that allows easily  |
|            |                      | finding the root IaC config of |
|            |                      | the resource                   |
+------------+----------------------+--------------------------------+
| git        | git_org              | The entity which owns the      |
|            |                      | repository where this resource |
|            |                      | is provisioned in IaC          |
+            +----------------------+--------------------------------+
|            | git_repo             | The repository where this      |
|            |                      | resource is provisioned in IaC |
+            +----------------------+--------------------------------+
|            | git_file             | The file (including path)      |
|            |                      | in the repository where this   |
|            |                      | resource is provisioned in IaC |
+            +----------------------+--------------------------------+
|            | git_commit           | The hash of the latest commit  |
|            |                      | which edited this resource     |
+            +----------------------+--------------------------------+
|            | git_modifiers        | The users who modified this    |
|            |                      | resource                       |
+            +----------------------+--------------------------------+
|            | git_last_modified_at | The last time this resource's  |
|            |                      | configuration was modified     |
+            +----------------------+--------------------------------+
|            | git_last_modified_by | The last user who modified     |
|            |                      | this resource                  |
+------------+----------------------+--------------------------------+
| simple     |                      |                                |
+------------+----------------------+--------------------------------+
| external   |                      |                                |
+------------+----------------------+--------------------------------+
```
