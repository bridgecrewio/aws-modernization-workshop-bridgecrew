---
title: "Setup your Bridgecrew account"
chapter: true
weight: 4
---

## Setup your Bridgecrew account

CloudFormation gives us total control to create, change, and delete resources in AWS. With [CloudFormation](https://bridgecrew.io/infrastructure-as-code-security/cloudformation/?utm_source=awsworkshop), it's easy to pick and deploy any of the hundreds of templates readily available from the [AWS sample templates](https://aws.amazon.com/cloudformation/resources/templates/). Because these templates are built solely with functionality in mind, it's also easy to forget important security configuration and end up having an insecure service running in production.

That’s why scanning your CloudFormation templates before deployment is so important. Bridgecrew integrates into your workflow and stops security issues before they can do any harm.

To get started, check that you have the following prerequisites:

- Python3 and 'pip'

    ```
    $ python3 -V
    Python 3.8.6

    $ pip3 -V
    pip 20.2.3 from /usr/local/lib/python3.8/site-packages/pip (python 3.8)
    ```

- An AWS account and an IAM user that can make programmatic calls.

    ```
    cat ~/.aws/credentials
    [default]
    aws_access_key_id = ABCDEFGHIJKLMNOPQRSTUVWXYZ1
    aws_secret_access_key = awssecretkeystring

    ```

- A Bridgecrew account. 

     [You can create one for free, here!](https://bridgecrew.cloud/?utm_source=awsworkshop)


- The Bridgecrew client CLI.

    The CLI works on Windows, Mac, and Linux. You can install it with pip.

    ```
    pip3 install bridgecrew
    ```

    If you run into problems, try the [alternate install instructions](https://docs.bridgecrew.io/docs/ingesting-scan-data#installation?utm_source=awsworkshop).



