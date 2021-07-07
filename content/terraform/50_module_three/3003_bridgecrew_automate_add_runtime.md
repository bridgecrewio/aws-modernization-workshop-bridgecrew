---
title: "AWS runtime scanning"
chapter: true
weight: 303
pre: "<b>6.3 </b>"
---

## Scanning runtime resources for vulnerable infrastructure

Let’s switch gears to address infrastructure that wasn't deployed by Terraform.

Greenfield infrastructure as code deployments are a luxury not many of us have. In reality, our AWS accounts have objects that were created manually for one reason or another. Transitioning to IaC is rarely a one-and-done affair, so you may have objects in your AWS accounts that are managed by a team that has not yet made the switch.

That’s why it’s important to scan objects directly in your AWS environment in addition to scanning your Terraform templates in git or as part of the CI/CD pipeline, as we’ve already shown.

Bridgecrew provides runtime scanning via an AWS integration, allowing full coverage of infrastructure security both before and after deployment.

### AWS Runtime Integration

To enable runtime scanning of your AWS account, goto the [**Integrations Tab**](https://www.bridgecrew.cloud/integrations) and select **AWS Read Only** under the **Cloud Providers** section.

![AWS Bridgecrew Integration](./images/dashboard-aws-runtime-00001.png "AWS Bridgecrew Integration")


{{% notice info %}}
<p style='text-align: left;'>
Read-only access is scoped as minimally as possible in order to give Bridgecrew only the necessary access to scan your AWS accounts.
</p>
{{% /notice %}}

Click **Add Account** then **Launch Stack** to enable the integration: 

![AWS Bridgecrew Integration](./images/aws-integration-add.png "AWS Bridgecrew Integration")

You will be taken to your AWS account to authorize the integration:

![AWS Bridgecrew Integration](./images/dashboard-aws-runtime-00003.png "AWS Bridgecrew Integration")

**Check the checkbox** to approve the IAM permission creations via our Terraform stack, and click **Create Stack**

![AWS Bridgecrew Integration](./images/dashboard-aws-runtime-00004.png "AWS Bridgecrew Integration")

You can track the progress of the stack creation within your AWS account, once completed, you'll see the integration turn green in the Bridgecrew dashboard!

![AWS Bridgecrew Integration](./images/dashboard-aws-runtime-00006.png "AWS Bridgecrew Integration")

Sucessful Integration: 
![AWS Bridgecrew Integration](./images/dashboard-aws-runtime-00007.png "AWS Bridgecrew Integration")

That’s all it takes to connect your AWS account to Bridgecrew for continuous cloud security monitoring and compliance benchmarking.

### Exploring runtime violations
With the runtime AWS account connected, let’s edit our filters on the Incidents page to show only the AWS source. In the filters option pane, select your AWS account ID that should now show up alongside your other integrations from the earlier modules.


![AWS Bridgecrew filter pane](./images/filter-aws-only-dash.png "AWS Bridgecrew filter pane")


{{% notice info %}}
<p style='text-align: left;'>
Unlike the rest of this workshop, the information displayed in your Bridgecrew Dashboard may differ from the images below, as no two AWS accounts will have the same content.
</p>
{{% /notice %}}

After setting our filter, we can browse through all the security and compliance violations detected in our live AWS account, 

In the example below, we can see an S3 bucket is not encrypted at rest. Selecting a resource from the group of resources on the right hand side will display much more information, including a Terraform representation of the AWS object in question:

![AWS Bridgecrew Integration](./images/dashboard-aws-runtime-00012.png "AWS Bridgecrew Integration")

Further context on the issue and remediation options is also available in the **Guidelines** tab.

![AWS Bridgecrew Integration](./images/dashboard-aws-runtime-00013.png "AWS Bridgecrew Integration")

Bridgecrew also alerts on account-wide settings such as user password policies and informational best practices, such as tagging each resource with ownership or purpose information:

##### Untagged Items in Account
![AWS Bridgecrew filter pane](./images/example-tagging-info.png "AWS Bridgecrew filter pane")

##### Weak Account Password Policy
![AWS Bridgecrew Integration](./images/dashboard-aws-runtime-00008.png "AWS Bridgecrew Integration")


### Identity and Access Management (IAM) Insights
Bridgecrew also analyzes AWS IAM roles, permissions, groups, and policies to identify unused and overly-permissive configurations.

You can use the filter pane to only show **Insights**, highlighting IAM specific issues:


![AWS Bridgecrew filter IAM Insights](./images/dashboard-aws-runtime-00009.png "AWS Bridgecrew filter IAM Insights")

IAM Insights will even provide a re-written, rightsized IAM policy document with only the permissions your applications are requesting of the role or policy. This helps you build and maintain least-privilege IAM and reduces the scope of abuse from a misconfigured or exploited application.

![Rightsizing an IAM policy](./images/iam-insights-rightsizing.png "Rightsizing an IAM policy")


