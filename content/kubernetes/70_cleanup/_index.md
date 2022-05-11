---
title: "Cleanup"
chapter: false
weight: 22
pre: "<b>7 </b>"
---

## Environment cleanup

Below are steps to remove the created environment, depending on which environment you used. You can choose to remove / delete everything, or you can keep your GitHub and Bridgecrew accounts if you previously did not have a user account.

If you are not sure whether the accounts were created specifically for the workshop, we recommend keeping them as a precaution. You can also reach out to the workshop host for assistance.


### Bridgecrew


You can keep your Bridgecrew.cloud account for free, however if you do require account removal, it can be achieved via the “user options” > “Usage”. in the bottom left corner of the dashboard. [https://docs.bridgecrew.io/docs/how-do-i-delete-my-account](https://docs.bridgecrew.io/docs/how-do-i-delete-my-account)

    
![alt_text](images/bcDeleteAccount.png "image_tooltip")
     
### AWS environment 


To remove the resources created in your AWS account by the workshop, complete these two steps.


### 1.

In **CloudFormation**, select the `bridgecrew-workshop` CloudFormation template. The template's status will read `CREATE_COMPLETE`. Select Delete.

You will then be asked to confirm by typing `Delete` into a prompt. This action will remove the VM and all associated access roles, the nested Kubernetes cluster, ArgoCD, and related codebases.

### 2. 
In Cloud9, choose the `bridgecrew-workshop` item under **Shared Environments** and select delete. This action will remove the connection to the Cloud9 IDE.	


### Go it alone (local setup)


The following commands will remove everything we installed locally following the **Local Setup** instructions. Please ensure you do not need any of these tools or repositories before uninstallation.

```bash
    # Remove KIND Cluster
    kind delete cluster –-name bridgecrew-workshop

    # Remove Checkov
    pipenv uninstall checkov || pip uninstall checkov

    # Remove yor container
    docker rmi bridgecrew/yor

    # Remove cloned kustomizegoat repository
    rm -rfv kustomizegoat/

    # Remove KIND CLI
    rm -v /usr/bin/kind

    # Remove kubectl CLI
    rm -v /usr/bin/kubectl
```