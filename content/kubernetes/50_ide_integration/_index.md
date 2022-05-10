---
title: "IDE integration"
chapter: false
weight: 18
pre: "<b>5 </b>"
---


## The new scenario 

![alt_text](images/weAreHere-m4-1.png "image_tooltip")


Now we have controls blocking severe security issues from our Kubernetes cluster, plus early warning systems like pull request scans that are directly in the developers' workflow.

But there is still some friction in this system because we still may need to make changes even after everything is committed and the pull request is raised.

To completely streamline this system, we’ll add the VSCode IDE plugin. This plugin will surface potential issues right at the point of development.


## Fixing before commit

The best issue is one that never even makes it into a Git commit. By highlighting potential issues in VSCode, we can achieve just that!

For this section, we’ll jump out of our pre-built environment. We can clone our KustomizeGoat fork directly onto our local machine in order to open within VSCode.

You can skip this section if you’d rather not touch your local machine setup. The rest of the workshop does not depend on this VSCode module, but it’s definitely worth walking through the steps together even if you decide not to work directly with your local machine.

Here we can see VSCode, with the Extensions sidebar open on the left. We can find and install the Checkov extension.

![alt_text](images/vsCodePlugin.png "image_tooltip")


The extension needs a Bridgecrew API key to function, like the one we created with the GitHub Action integration, and can be entered by clicking on the new **Checkov** status item on the blue bar at the bottom of the VSCode window:


![alt_text](images/vsCodeCheckovBar.png "image_tooltip")


Checkov is currently scanning the `kustomize/base/deployment.yaml` file within our KustomizeGoat repository. Checkov will scan any IaC file when opened in VSCode.
 
Once the scan is complete, any issues found will be annotated and underlined in red onto the Kubernetes objects themselves.

![alt_text](images/vsCodeSqiggle.png "image_tooltip")

Hover over the red underlined object to get more context and to view a list of all the same issues that we saw in our CI/CD pipeline and pull requests.

![alt_text](images/vsCodeProblemList.png "image_tooltip")

If we want, we can see this same information presented in a different way.  Open the VSCode **Problem** pane to see Checkov’s findings separated from the code display.


![alt_text](images/vsCodeProblemsBottom.png "image_tooltip")

![alt_text](images/vsCodeAnnotationStyle2.png "image_tooltip")


## Kubernetes mode versus Kustomize mode

In VSCode, Kubernetes objects are scanned and annotated as they are found. At this stage, it does not make sense to render a resulting Kustomize manifest, so any valid Kubernetes objects, per-file, will be scanned as-is.

This means that results can vary slightly from VSCode and the fully rendered Kustomize environments in CI/CD to our Admission Controller checks. However, enforcing the same policies in all these locations will streamline the developer’s work process as they implement DevSecOps and a more secure IaC posure for their organization.

## Congrats, that's all for IDE enablement!

At the time of this workshop, we also support [**IntelliJ**](https://docs.bridgecrew.io/docs/jetbrains) with the same style of plugin. Check it out if interested from the *Integrations* page in *Bridgecrew*.
