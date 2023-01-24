---
title: "DEFEND THE BANK! PART 1: FIX THE K8S MANIFEST"
chapter: false
weight: 18
pre: "<b>5 </b>"
---


## GET YOUR WHITE HATS ON!

We've seen how dangerous having a critical vulnerability in an application, in combination with a default, or worse lazy, deployment manifest can be. If we can get access to an underlying host we can establish a persistent hacker presence. From there we can:

- Run Crypto mining
- Scan the networks for ports that might be open allowing us to move laterally through the network
- Query the metadata server to see if we have access to via cloud services and potential take over the cloud infrastruture or access private S3 data!

Let's start this task by preventing us from being able to break out of the container and gain access to the host node filesystem for starters.

### Step 1
Go to the AWS Console and from there go to CodeCommit where we will find the code for the Log4jankybank application. In our CodeBuild section we'll see that our fellow security colleagues have installed the open source tool Checkov to the JankyBank-Build project to scan for problems in our application.

They have added a specific flag to the Checkov command line to ensure it only "soft fails".
That means it will not break the build but we can see the security issues.

Your first task is to remove the flag that makes it soft fail so we do fail the build.

Check here to find out what that command line option is and modify the buildspec so that our security tools will break the build and stop a vulnerable application from deploying.

### Step 2

Now take a look at the results from our last build, specifically the Reports section.
There will be one big problem with the manifest. What is it?

Fix this problem in the kubernetes manifest found in CodeCommit. You'll need to remove 2 lines from the manifest, commit the new code. The good news is that CodePipeline is smart, will detect the change code and automagically reattempt to build and deploy our app.

We did set our buildspec to hard fail so this time it will hard fail and that's ok.

We'll fix the remaining security issues in our next task!


