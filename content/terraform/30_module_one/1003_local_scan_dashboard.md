---
title: "Bridgecrew Dashboard"
chapter: true
weight: 103
pre: "<b>4.3 </b>"
---

## Viewing results in Bridgecrew

You just scanned your Terraform templates locally using Checkov. If you included your API key, the results were sent to the [Bridgecrew platform](https://bridgecrew.cloud) for further investigation. You may have noticed the URL at the end of the CLI scan. That’s a direct link to the results in Bridgecrew.

Click on that link to bring up that scan’s Code Review page. This is a list of all of the misconfigurations identified from that scan grouped by resource and labeled by severity.

![Bridgecrew Code Review](images/code_review.png "Bridgecrew Code Review")

In a later section, we’ll review the [Projects page](https://www.bridgecrew.cloud/projects), which is an aggregated view of the different Code Reviews across all scan types.
