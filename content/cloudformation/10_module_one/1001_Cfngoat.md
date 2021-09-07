---
title: "CfnGoat"
chapter: true
weight: 101
pre: "<b>4.1 </b>"
---

## Vulnerable-by-design demo repository setup


This workshop uses our vulnerable-by-design CloudFormation project, CfnGoat, so that you can scan and automate infrastructure code without the added friction of integrating your own code. Simply clone the open-source project’s repository:

```bash
git clone https://github.com/bridgecrewio/cfngoat.git
cd cfngoat
git status
```

Sample output:

```bash
$ git clone https://github.com/bridgecrewio/cfngoat.git
cd cfngoat
git status
Cloning into 'cfngoat'...
remote: Enumerating objects: 64, done.
remote: Counting objects: 100% (64/64), done.
remote: Compressing objects: 100% (54/54), done.
remote: Total 64 (delta 18), reused 33 (delta 7), pack-reused 0
Unpacking objects: 100% (64/64), 73.62 KiB | 718.00 KiB/s, done.

On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean

➜  cfngoat git:(master)
```
