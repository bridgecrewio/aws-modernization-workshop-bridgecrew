---
title: "Setup git"
chapter: true
weight: 5
---


## Check your local git installation

To ensure your local git client is setup correctly, try the following commands, you should not receive an error from any of them, and end up with a copy of our 'vulnerable by design' training project "CFNGoat" on your machine, which we'll use later! 

```
git clone https://github.com/bridgecrewio/cfngoat.git
cd cfngoat
git status
```

Sample output:

```
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
