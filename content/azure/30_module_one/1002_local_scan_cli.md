---
title: "Checkov"
chapter: false
weight: 102
pre: "<b>4.2 </b>"
---

{{% notice info %}}
If you are running Checkov with the Bridgecrew API token and you use a proxy, you may need to turn off your VPN/proxy or use the `--ca-certificate` flag to allow your proxy's certificate using the directions here: https://github.com/bridgecrewio/checkov/pull/1099. If you run Checkov without the Bridgecrew API token, this won't be an issue.
{{% /notice %}}

## Run Checkov locally

To demonstrate what kinds of security and compliance errors Bridgecrew can identify in Terraform templates, start by using Checkov and send the results to the Bridgecrew platform.

Make sure you are in the cloned directory from the previous step, copy your unique Bridgecrew API token, and scan the `storage.tf` in the `azure` directory:

```bash
checkov -f terraform/azure/storage.tf --bc-api-key $YOUR_BC_API_KEY --repo-id bridgecrewio/storage
```

You can also scan entire directories with -d <path>, such as the `azure` directory:

```bash
checkov -d terraform/azure/ --bc-api-key $YOUR_BC_API_KEY --repo-id bridgecrewio/azureterragoat
```

You can use Checkov without `--bc-api-key` to display the results in the command line without uploading to the Bridgecrew platform for testing or local-only scan results.

The results will show all the failed policies and link to guides explaining the rationale behind each misconfiguration and steps to fix them. Note the output also includes the filename and snippet of code that is misconfigured:

![Checkov scan results](./images/checkov_terragoat.png "Checkov scan results of the TerraGoat repository")

In the example output above, you can see that Bridgecrew identified two failing policies: “Ensure that managed disks use a specific set of disk encryption sets for the customer-managed key encryption” and “Ensure Azure managed disk has encryption enabled”.

To get the list of policies that Checkov checks for, use `-l` or `--list`:

```bash
checkov --list
```

Checkov policies
In many instances, when testing locally with the Checkov, you may only be interested in running just a few policies. In that case, you can add the `-c` or `--check` option:

```bash
checkov -f terraform/azure/storage.tf -c CKV_AZURE_93,CKV_AZURE_2
```

Alternatively, if you want to run all but a few policies, use the `--skip-check` option:

```bash
checkov -f terraform/azure/storage.tf --skip-check CKV_AZURE_93,CKV_AZURE_2
```