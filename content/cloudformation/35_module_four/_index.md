---
title: "Module - Trace"
chapter: false
weight: 300
pre: "<b>7 </b>"
---

So far, we've seen how Bridgecrew provides automation to help your developers block bad infrastructure PR's, remediate current issues, and provide infrastructure security at each stage of the DevOps pipeline.

However, an often overlooked continuation of this process is to answer the "why". 

## "Why"
- Why was this resource misconfigured in the first place?
- Which teams or applications may be impacted by a remediation of an existing cloud resource?
- When did this configuration first appear in our application codebase?

Automated tracing allows us to answer these questions easily, and compliments Checkov in our CI pipelines and the Bridgecrew policy integrations perfectly.

## Code to Cloud tracing with Yor
Bridgecrew's new open source tool, [yor.io](https://yor.io) enables automated code-to-cloud tracig of objects, by automatically and intelligently tagging infrastructure as code objets in your CI/CD pipeline.

This allows us to categorically understand which block of IaC created which cloud objects, when, where and how.

Lets take a quick trip into your, to round off our infrastructure security journey.

## Module Learning Objectives
- Automatically tag IaC resources with Yor
- Deploy tagged resources to AWS
- Learn how Yor's automated resource tags allow developers and security teams to easily answer infrastructure questions.

