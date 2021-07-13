---
title: "Bridgecrew platform results"
chapter: true
weight: 301
pre: "<b>6.1 </b>"
---

## Investigating security violations in Bridgecrew

Providing feedback in IDEs and CI/CD pipelines provides valuable insights into the posture of your code. Bridgecrew provides a centralized view for tracking misconfigurations across your code scans and runtime environments. We’ll start with the view across code scans.

Navigate to the [Projects](https://www.bridgecrew.cloud/projects) tab in the Bridgecrew platform. Here you can see the results of your GitHub scan, as well as any other code scan that includes a repository ID and your Bridgecrew API.

![Bridgecrew Projects page](images/bridgecrew_projects.png "Bridgecrew Projects page")

This page comes packed with information and navigation tools for misconfigurations identified. 

* Use the filters on the left to narrow down violations, or the top to narrow down to previous git modifiers.
* Search for code snippets or tags in the top. 
* See dependent resources and audit histories on the right side.

Hit next to learn how to create a pull request with automatic fixes!