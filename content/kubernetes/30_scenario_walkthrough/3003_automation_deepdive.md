---
title: "Automation deep dive"
chapter: false
weight: 12
pre: "<b>3.3 </b>"
---

While doing things manually is *NOT* what we want for a DevSecOps pipeline, for the sake of understanding the current setup a little more, lets see what it looks like if the developer was to try and apply the dev environment directly to the kubernetes cluster using the CLI, `kubectl`.

This will render the kustomize template and pass it to the kubernetes API, we should see the same results from the API as we saw through Argo, with our admission controller rejecting the deployment…

```
kubectl create namespace kustomizegoat

kubectl apply -k ./kustomizegoat/kustomize/overlays/dev
```



![alt_text](images/admissionControllerManualKubeCtl.png "image_tooltip")


## Unwrapping the Checkov admission controller

Because the admission controller is powered by Checkov, Bridgecrew’s open-source security scanning tool,we can simulate the failure by having Checkov scan the local Kustomize manifests. This way, we don’t need to have a Kubernetes cluster.

To do this, try running `checkov -d ./kustomizegoat --framework kustomize` in the Kustomize directory. The CLI output will be very similar to what we have already seen in Bridgecrew from the admission controller.

Here you will see all the policy results from Checkov for all of our overlays and base directories. The admission controller has a configurable list of specific policies it rejects, but this Checkov output will show all severities.


![alt_text](images/checkovExampleError.png "image_tooltip")

![alt_text](images/CheckovPassedChecks.png "image_tooltip")
