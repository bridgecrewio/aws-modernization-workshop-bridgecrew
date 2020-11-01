---
title: "Cloud DevSecOps with Bridgecrew"
chapter: true
weight: 1
---

# Welcome!

In this workshop, you will learn how to save time, improve your security posture, and make your dev and security team's lives easier!

You'll do this by getting hands on and automating your infrastructure security from code to commit, using Brigecrew and the AWS developer tools suite to take up most of the strain!

But before we jump in blind, lets provide a little context! 

## DevSecWhat?

DevSecOps as a term gets banded about quite a lot, so what do we mean, and why should you care?

Traditionally, development, operations and security teams were seperate, each with very specific responsabilities. However, with cloud providing self service, and the merging of development and operations teams, it's now incredably common for development teams to deploy their own infrastructure, adding capacity and new technologies to rapidly bring new features and products online.

With this shift, often referred to as "DevOps", two of those teams have merged, adopting development practices such as CI/CD, and source controlled manifests (gitops) to safley and repeatably manage, maintain and control cloud infrastructure deployments, and ultimatley, the team's code/product/app/site.

### Performance Benefits
 These two teams becoming one allows a single pipeline of automation which satisfies both the developers and operational concerns and needs for allowing code to make it into production. Once in place, this means developers can focus on features and fixes, rather than the often manual back and forth with operations teams, and the operations engineers in the team can ensure that requirements for testing, scaling and monitoring the infrastructure are baked into the release lifecycle.

 The result; as many deploys a day as you want, more code, more fixes, more features in production quicker. less manual messing about.

### The secutity elephant in the room
With deployments to production now happening 10's or potentially hundreds of times a day, and the development team in control of their own cloud infrastructure, a number of traditional security team concepts break down.

For example, AWS operates a "Shared Responsability" model with it's users, pushing responsability for securing the infrastructure they deploy onto the development team.

Alongside this, the rate of deployments, often onto containerised, lambdas, or other styles of "short lived" deployments make visibility, security monitoring and, security validation and breach detection complicated for a traditional security team.

### Security can also build requirements into the dev pipeline!
In the same way as operations enineers can build their monitoring and alerting requirements into the development pipeline, security scanning and enfocement can be included too. **DevSecOps is the term we use to describe this.**

You may also be familiar with the term "Security Champion", a member of the team with a passion and knowledge for ensuring secure practices within a DevOps team, DevSecOps is what happens when this security champion automates security best practices into the teams development pipelines, while working with the team to ensure understanding of why, and the importance of security visibility.

**If you don't have a Security Champion, consider the Bridgecrew platform a virtual one, we'll show you how it takes the effort out of automating security insights into your environments!**

## Security as a guardrail, not a roadblock!
Just as many a developer and operations engineer would sigh, pre DevOps, when having to work with the other team, security is often seen as a decellerator, slowing down a features progression to production.

Historically, all of these teams had very different goals, which caused friction

### Developers 
#### Measured on new features, bugs fixed
### Operations
#### Measured on stability of the production environment
### Security
#### Measured on the security posture, acreditation and protecting the business.

Within a DevSecOps team, responsabilities are understood and shared, while obviously an individuals focus may differ, a team moving forward a single unit, responsible for the total ownership of the deployment, allows for a more mindful approach.

Security automated inside a teams DevOps pipeline can provide insight and early warnings to the team, without blocking or slowing down the productivity of the team, it gives the Security engineers early enough visibility into the development and infrastructure efforts, so that action can be taken, even fully automated which would historically be a prevention of deployment or rollback once in production, which is often where the impression of a roadblock came from.

## Lets get started!
Bridgecrew is committed to making the integration of security into every day developer tooling as simple, effective and painless as possible, lets show you how the Bridgecrew platform automates a lot of what we've just discussed, giving your developers cricual insights and tools to improve and maintain your security posture!

