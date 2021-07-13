---
title: "AWS fixes in runtime"
chapter: true
weight: 304
pre: "<b>6.4 </b>"
---

## Automating fixes in runtime

Similar to what we did with pull request fixes in the previous module, Bridgecrew allows for immediate remediation of issues in runtime by reconfiguring your objects via the AWS APIs.

Implementing automated remediations does require extra permissions than previously granted with the default AWS Read Only integration. When you attempt a runtime remediation without the correct permissions, you’ll be prompted to configure the AWS Remediation Stack: 


![AWS Bridgecrew Integration, Remediate](./images/dashboard-aws-runtime-00010.png "AWS Bridgecrew Integration, Remediate")

Adding the AWS Remediation stack follows the same workflow as the previous read-only AWS integration:

![AWS Bridgecrew remediation integration](./images/remediate_stack_1.png "AWS Bridgecrew remediation integration")

Select **Create Stack** and return to Bridgecrew, you will now be able to Remediate runtime resources:
![AWS Bridgecrew remediation integration](./images/remediate_stack_3.png "AWS Bridgecrew remediation integration")

## Fixing an unencrypted S3 bucket

Continuing with the example of the unencrypted S3 bucket from the previous page, the **Remediate** button will now allow runtime changes to the S3 configuration:

![AWS Bridgecrew remediating s3 unencrypted bucket](./images/remediation-s3-encryption-00001.png "AWS Bridgecrew remediating s3 unencrypted bucket")

For the sake of this workshop, we can use the AWS Console to confirm the selected bucket is currently unencrypted:

![AWS Bridgecrew remediating s3 unencrypted bucket](./images/remediation-s3-encryption-00006.png "AWS Bridgecrew remediating s3 unencrypted bucket")

Back in Bridgecrew, review the remediation, and select **Remediate** a final time.

![AWS Bridgecrew remediating s3 unencrypted bucket](./images/remediation-s3-encryption-00007.png "AWS Bridgecrew remediating s3 unencrypted bucket")

Bridgecrew will now use AWS API's to ensure encryption is turned on for the selected resource:

![AWS Bridgecrew remediating s3 unencrypted bucket](./images/remediation-s3-encryption-00008.png "AWS Bridgecrew remediating s3 unencrypted bucket")

Checking the resource once more in the AWS Console, you will see that encryption is now enabled:

![AWS Bridgecrew remediating s3 unencrypted bucket](./images/remediation-s3-encryption-00009.png "AWS Bridgecrew remediating s3 unencrypted bucket")

The violation will also have been marked resolved in the Bridgecrew **Incidents** page.

Instead of resolving issues in production, if you follow GitOps best practices, we should prevent changes in production. We'll cover how to handle drift in the next session.