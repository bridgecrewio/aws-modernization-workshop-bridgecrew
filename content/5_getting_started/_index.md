---
title: "DevSecWhat?"
chapter: false
weight: 2
---

## DevSecWhat?
The foundation of DevSecOps lies in the DevOps movement, wherein development and operations functions have merged to make deployments faster, safer, and more repeatable. Common DevOps practices include automated infrastructure build pipelines (CI/CD) and version-controlled manifests (GitOps) to make it easier to control cloud deployments. By baking software and infrastructure quality requirements into the release lifecycle, teams save time manually reviewing code, allowing them to focus more on shipping features.

As deployments to production speed up, however, many traditional cloud security concepts break down. With the rise of containerized technologies, serverless functions, and IaC frameworks (which we’ll dig into in the next section), it’s harder to maintain cloud security posture visibility. 

By leveraging DevOps foundations, security and development teams can build security scanning and policy enforcement into automated pipelines. The ultimate goal with DevSecOps is to “shift cloud security left.” That means automating it and embedding it earlier into the development lifecycle so that actions can be taken earlier. Preventing risky deployments is a more proactive approach to traditional cloud security that often slows down development teams with deployment rollbacks and disruptive fixes.

For DevSecOps to be successful for teams working to build and secure infrastructure, embracing existing tools and workflows is critical. At Bridgecrew, we’re committed to making it as simple, effective, and painless as possible to automate cloud security and integrate it seamlessly into release lifecycles.



{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Bridgecrew and AWS services can be architected to build a solution while demonstrating best practices along the way. These examples, especially the intentionally vulnerable "CFNGoat" repository, are not intended for use in production environments.
</p>
{{% /notice %}}
 



