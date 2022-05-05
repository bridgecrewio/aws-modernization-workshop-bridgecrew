---
title: "Cleanup"
chapter: false
weight: 22
pre: "<b>7 </b>"
---

## Environment Cleanup

Below are steps to remove the created environment, depending on which environment you used. You can choose to remove / delete everything, or keep your accounts (such as Github and Bridgecrew) if you previously did not have a user account.

If you are not sure whether the accounts were created specifically for the workshop or pre-existed, we recommend keeping them as a precaution, you can also reach out to the workshop host for assistance!


### Bridgecrew


You can keep your Bridgecrew.cloud account for free, however if you do require account removal, it can be achieved via the “user options” > “Usage”. in the bottom left corner of the dashboard. [https://docs.bridgecrew.io/docs/how-do-i-delete-my-account](https://docs.bridgecrew.io/docs/how-do-i-delete-my-account)

    
![alt_text](images/bcDeleteAccount.png "image_tooltip")
     
### AWS Environment 


To remove the resources created in your AWS account by the workshop, complete these two items.


### 1.

In *CloudFormation*, select the `bridgecrew-workshop` cloudformation template which will have the `CREATE_COMPLETE` status, and chose Delete.

You will then be asked to confirm by typing `Delete` into a prompt, this will remove the VM and all associated access roles with the workshop, as well as the nested kubernetes cluster, argoCD and related codebases.

### 2. 
In Cloud9, chose the `bridgecrew-workshop` item under “Shared Environments” and select delete, this will remove the connection to the Cloud9 IDE, which is already being removed as it was hosted on the resources we deleted in step one, above.	



### Go it alone (optional local setup)


The following commands will remove everything we installed locally following the “Local Setup” instructions. Please ensure you do not need any of these tools or repositories before uninstallation!

```
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
