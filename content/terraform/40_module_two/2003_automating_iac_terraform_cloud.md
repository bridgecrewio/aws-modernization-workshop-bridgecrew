---
title: "Terraform Cloud"
chapter: false
weight: 204
pre: "<b>5.3 </b>"
---

{{% notice info %}}
<p style='text-align: left;'>
A new, native integration between Bridgecrew and Terraform Cloud is coming soon! Check out the HashiCorp keynote for a preview: https://youtu.be/ZzLZaWUve4M?t=1387
</p>
{{% /notice %}}


## Leveraging Terraform Cloud and Sentinel for Bridgecrew scans

Bridgecrew has a native integration with Terraform Cloud that leverages Sentinel for policy controls. This means any commit that is pushed to Terraform Cloud will run through a Bridgecrew scan, identifying policy violations, blocking misconfigured builds, and detecting drift, all from the same place that you collaborate on Terraform templates, automate deployments, and store state.

{{% notice info %}}
Sentinel is a paid add-on. If you want to try this out for free, HashiCorp does offer a free trial. If you prefer not to sign up for the trial, feel free to skip this section and the "drift detection" section.
{{% /notice %}}

To sign up for the free trial of Terraform Cloud’s Team & Governance plan, go to your Terraform Cloud instance. Select “Settings” and “Plan & Billing.” Choose the Trial option. You should see Policies and Policy Sets show up in the left navigation menu.

![Terraform Cloud plans](images/terraform_cloud_signup.png "Terraform Cloud plans")

You need to add your TerraGoat repository to Terraform Cloud. Go to “Workspaces” and select “Create one now.”

![Terraform Cloud new workspace](images/terraform_cloud_new_workspace.png "Terraform Cloud new workspace")

Select “Version control workflow”:

![Create a version control workflow](images/terraform_cloud_create_workspace.png "Create a version control workflow")

Select “GitHub” and choose your TerraGoat repository we previously forked:

![Add GitHub](images/terraform_cloud_add_github.png "Add GitHub")

Name the workspace `terragoat` and open the “Advanced options” and add the directory `/terraform/simple_instance/` (we'll be adding that directory later). This will focus the scans to just the aws templates. Turn on "Automatic speculative plans" to create plans for pull requests. Select “Create workspace”:

![Config settings](images/terraform_cloud_config_settings.png "Config settings")

Select “Configure variables” and add your AWS Account and Access Keys as environment variables called `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`. If you aren’t sure where to find the keys, see [this guide](https://docs.aws.amazon.com/powershell/latest/userguide/pstools-appendix-sign-up.html).

![Add environment variables](images/terraform_cloud_env_variables.png "Add environment variables")

Go to Settings and select General. From this settings screen, grab your workspace ID for the next step.

![Grab your workspace ID](images/terraform_cloud_workspace_id.png "Grab your workspace ID")

Grab the API token from Terraform Cloud for the integration. Go to the [API token menu](https://app.terraform.io/app/settings/tokens) (User -> Settings -> Tokens) and select “Create an API token.”

![Terraform Cloud API token](images/terraform_cloud_api_token.png "Terraform Cloud API token")

Copy that API token for the next step.

Next, you’ll add the Bridgecrew integration. Head over to the [Integrations](https://www.bridgecrew.cloud/integrations) screen in the Bridgecrew platform. Scroll down and select Terraform Cloud and Add Workspace. Fill in the Workspace ID, workspace name, and API token from the previous steps:

![Add TFC details to Bridgecrew](images/bc_tfc_details.png "Add TFC details to Bridgecrew")

Selecting “Create Policy” will generate a Sentinel Policy that you can then add to Terraform Cloud.

Head back to Terraform Cloud and go to the “[Policies](https://app.terraform.io/app/bridgecrew-demo/settings/policies)" setting and "Create a new policy." Name the policy `bridgecrew` and paste the code you copied in the Bridgecrew integration page and paste it into the “Policy code” section and select “Create policy”:

![Add Sentinel Policy](images/sentinel_policy.png "Add Sentinel Policy")

Select “[Policy Sets](https://app.terraform.io/app/bridgecrew-demo/settings/policy-sets)” and “Connect a new policy set”. You can create a versioned policy set, but for the sake of this workshop, go without a VCS connection. Name your setting and choose the `terragoat` workspace and select “Connect policy set”.

![Connect the policy set](images/terraform_cloud_connect_policy_set.png "Connect the policy set")

Go back to the “[Policies](https://app.terraform.io/app/bridgecrew-demo/settings/policies)” section and select the policy you made. Scroll down to the “Policy Sets” section and add the `terragoat_set` you made.

![Policy sets](images/terraform_cloud_policy_sets.png "Policy sets")

Finally, go to your workspace's main page and queue a run; don't worry if it fails, this just primes the runs to be automated with future GitHub pull requests.

![Queue a plan](images/tfc_queue.png "Queue a plan")

**Your Terraform Cloud integration is ready to go!**