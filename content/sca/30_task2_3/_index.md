---
title: "Hack the Bank! Pt 1: RECONNAISSANCE"
chapter: false
weight: 9
pre: "<b>3 </b>"
---

Log4janky Bank have an EKS cluster with their log4jankybank container image proudly running their banking front-end application.

As a Black Hat hacker we need to find out of there is any part of the deployment that is vulnerable.

NOTE: If you are using a VPN the Bank URL may not resolve because it is using http (not https) and a specific/new IP address. Some laptop security tools automatically block such URLs (like PANW's awesome Global Protect). If you can disable it temporarily, please do.

You can find the banks URL in the output section of the CloudFormation we ran in setup.

You should see a page which looks like this:

![alt_text](./30_task2_3/images/log4jankybankscreen.png "image_tooltip")


{{% notice info %}}
Hacking tip #1: Error messages can be revealing
Try logging in with some bad credentials.
This can be any credentials eg. login: johnny password: rotten
{{% /notice %}}


You will be brought to an error screen which indicates that for "security reasons" your details have been logged.

**Interesting!**

Wasn't there a rather public vulnerability with regards to a certain Log4j logging utility in 2021? One that has proven difficult to patch at scale. Perhaps we have stumbled upon a potential victim for a Log4shell attack!

