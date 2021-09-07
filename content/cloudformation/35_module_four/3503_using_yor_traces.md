---
title: "Using Yor Tracing"
chapter: true
weight: 353
pre: "<b>7.3 </b>"
---

# Using Yor traces in runtime

## Easily find Cloud Resources based on git information

Once our resources are deployed, we now have multiple ways to find, link and correlate between the who and what of our IaC actions in git, and the real resources running in our cloud environment.

For example, we can use the bridgecrew dashboard resource explorer, to query for all runtime resources in our AWS account which were last modified by `matt-at-bridgecrew.io`:

![Yor traceing with Bridgecrew dashboard](./images/yor-trace-resource-0.png)

Drilling down into the results, we'll see this easy searching for resources is powered by the Yor tags:

![Yor traceing with Bridgecrew dashboard](./images/yor-trace-resource.png)

## Easily find an IaC object from the AWS dashboard

Equally, a specific item in AWS can be located in your IaC codebase using the unique Yor trace ID across your git repository:

![AWS S3 bucket with issue](./images/s3-bucket-aws-issue.png)

By looking at the tags, we can use the unique `yor_trace` to search for the specific terraform object in git:

![AWS S3 bucket with issue](./images/s3-bucket-tags.png)

Easily finding the resource we need to fix:

![AWS S3 bucket with issue](./images/search-git.png)

# Learn more about yor!

For usecases from IAM management, tag based access controls to cost center management, check out [https://yor.io](https://yor.io)

