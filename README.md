# AWS modernisation workshop - DevSecOps with Bridgecrew
## Overview

This repo is home to the raw content for the "DevSecOps with Bridgecrew" AWS modernisation workshop. Hosted on the awsworkshop.io site [here.](https://bridgecrew.awsworkshop.io/)

The workshop walks you through everything needed for securing your IaC deployments, from "what is devsecops", PR scanning, pipeline setup and having your CI/CD pipeline automatically check for infrastructure as code issues before deployment to AWS!

## Viewing the content locally

You likley want to use the online version, by visiting [https://bridgecrew.awsworkshop.io/](https://bridgecrew.awsworkshop.io/)


However if you want to render the content locally, for testing, editing, or submitting a PR:

* install [hugo](https://gohugo.io/)
    * macOS: `brew install hugo`
    * Windows: `choco install hugo -confirm`
* clone this repo
* execute in the root folder:
  * `git submodule init`
  * `git submodule update --recursive --remote`
* run ```hugo server```
* The `hugo server` command will provide a localhost URL to view the content in a browser.

## References
* [Bridgecrew](https://bridgecrew.io)
* [AWS modernisation workshops](https://awsworkshop.io/)
* [AWS workshop content documentation guide](https://aws-samples.github.io/aws-modernization-workshop-sample/)
* [AWS sample workshop layout](https://github.com/aws-samples/aws-modernization-workshop-sample)