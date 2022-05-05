---
title: "Kubernetes Runtime"
chapter: false
weight: 21
pre: "<b>6.2 </b>"
---



## Kubernetes Runtime

Great! Now lets add insight into our already-running Kubernetes workloads too!  
In the integrations page, once again click *“ADD INTEGRATION”*


![alt_text](images/bcButtonAddIntegration.png "image_tooltip")


Then, from the *Cloud Providers* section, chose *Kubernetes*:


![alt_text](images/bcIntegrationsCloudProviders.png "image_tooltip")


Create a new API key for the integration and click “*CREATE”*:


![alt_text](images/bcIntegrationK8sAPIKey.png "image_tooltip")


Give the *cluster a name*, this is used to identify the Kubernetes cluster within Bridgecrew.


![alt_text](images/bcIntegrationCreateK8sCluster.png "image_tooltip")


Finally, select your kubernetes version (>0.19 or &lt;0.19) and *copy the provided kubectl commands:*


![alt_text](images/bcIntegrationKubernetesCliForCopy.png "image_tooltip")


Next, we simply *run the Kubectl commands* provided to enable the runtime integration in our Kubenetes cluster: 


![alt_text](images/kubectlRuntimeK8sIntegration.png "image_tooltip")


By running `kubectl get cronjob –namespace bridgecrew` we can see the bridgecrew runtime agent, scheduled to run and keep bridgecrew updated with the runtime posture of the cluster.


![alt_text](images/bcK8sCronjobget.png "image_tooltip")


Instead of waiting for the first scheduled run, lets manually run the job the first time so we can see data in the Bridgecrew dashboard: 

`kubectl create job --from-cronjob/bridgecrew manual-bc-runtime-scan --namespace=bridgecrew`

![alt_text](images/kubectlCreateJobRuntimeScan.png "image_tooltip")


_We will now start to see data under the incidents tab in the Bridgecrew dashboard, you can check on the status of the Job’s instance with the `kubectl get job` command also.


![alt_text](images/kubectlGetJobKickoffRuntimeScan.png "image_tooltip")


In the *Incidents* tab, which covers *only* runtime-related events, we will be able to filter on our new cluster name, to see issues with the current running pods and services.

Some of these are core kubernetes services which require more access than regular hosted applications, so we’ll be looking at how to suppress and create suppression rules for certain items, as well as fixing up our buggy dev environment code in future workshops!


![alt_text](images/bcIncidentsPageK8SCluster.png "image_tooltip")



### Congratulations, Runtime scanning is enabled!
