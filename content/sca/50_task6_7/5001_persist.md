---
title: "DEFEND THE BANK! PART 2: FIX THE APPLICATION"
chapter: false
weight: 19
pre: "<b>5.1 </b>"
---

## We're on the home stretch now.

Fixing the manifest means that anyone exploiting the log4j vulnerability will no longer be able to execute an easy container breakout. Unfortunately the build is still breaking due to our log4j vulnerability so we'll need to fix that before we're secure and can deploy our application again.

We need to fix the version of log4j that we're using but first we'll need to know what version to upgrade to and where to upgrade it in our application.

Let's start by finding out what version we need.

Go to CodeBuild again like we did last time and look at the remaining vulnerabilities.

We can see there's more than our headline grabbing log4shell `CVE-2021-44228`.

Often when a major vulnerability like this comes to light, the fixes themselves have further issues resulting in a cascade of documented issue and CVEs. In our case `CVE-2021-44228` gave rise to

- CVE-2021-44832
- CVE-2021-45046 
- CVE-2021-45105

Take a look at the build report and specifically the recommend fix version for each of the vulnerabilities and see if there is one version to fix them all.

This is a Java application so our dependencies are all listed in a specific XML file. Find this file, upgrade log4j, save the new version.

Changing the code will automatically initiate a new pipeline so head over to CodePipeline to see if it succeeds and if we have fixed all of our security issues.

If it works, our application and manifest will pass our security tests and be redeployed as a much safer bank.

If the build has been successful, enter the version of Log4j you used above to let the SOC team know and record your success!##