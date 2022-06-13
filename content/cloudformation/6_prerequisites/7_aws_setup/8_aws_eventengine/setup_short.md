---
title: "Quick Setup"
chapter: false
weight: 17
pre: "<b>3.2.1.5 </b>"
---

{{% notice info %}}
We are going to install jq and initilize a python enviroment. Cloud9 already has the latest version of Python installed. 
{{% /notice %}}

Install jq - jq is a command-line tool for parsing JSON.
```sh
sudo yum install jq
```
Start a python enviroment 
```sh
python3 -m venv env
source ./env/bin/activate 

```
