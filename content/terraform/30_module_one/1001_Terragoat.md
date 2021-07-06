---
title: "TerraGoat"
chapter: true
weight: 101
pre: "<b>4.1 </b>"
---

## Vulnerable-by-design demo repository setup

This workshop uses our vulnerable-by-design Terraform project, TerraGoat, so that you can scan and automate infrastructure code without the added friction of integrating your own code. Simply clone the open-source project’s repository:

```bash
git clone https://github.com/bridgecrewio/terragoat.git
cd terragoat
git status
```

Sample output

```bash
$ git clone https://github.com/bridgecrewio/terragoat.git
cd terragoat
git status
Cloning into 'terragoat'...
remote: Enumerating objects: 10, done.
remote: Counting objects: 100% (10/10), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 581 (delta 2), reused 0 (delta 0), pack-reused 571
Receiving objects: 100% (581/581), 221.43 KiB | 4.26 MiB/s, done.
Resolving deltas: 100% (269/269), done.

On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```