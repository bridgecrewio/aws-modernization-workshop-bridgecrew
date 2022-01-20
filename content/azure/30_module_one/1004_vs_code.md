---
title: "VS Code Plugin"
chapter: false
weight: 104
pre: "<b>4.4 </b>"
---

## Run Checkov in your IDE

You can get feedback directly in your integrated development environment (IDE) using Bridgecrew’s Checkov Visual Studio Code [extension](https://marketplace.visualstudio.com/items?itemName=Bridgecrew.checkov). The tool highlights misconfigurations inline and in development environments—like spell check for IaC misconfigurations.

First, you need to install the extension. In VS Code, go to Extensions and search for `Checkov`. Click Install.

![Install plugin](images/vs_code1.png "Install plugin")

Next, go to the Checkov **Extension Settings** and paste the API Token from the Bridgecrew platform that we saved earlier.

![Add API key](images/vs_code2.png "Add API key")

Scan the TerraGoat `instance.tf` file using the extension. Go to File -> Add Folder to Workspace and navigate to the cloned TerraGoat directory. Add /terraform/azure to your VS Code workspace and open `instance.tf`.

![See the scan results](images/vs_code3.png "See the scan results")

Checkov will immediately start scanning and will highlight any identified misconfigurations, with red underline. Move your cursor over the second code block `resource azurerm_linux_virtual_machine "linux_machine"`. Checkov has identified multiple misconfigurations, including “Ensure Virtual Machine Extensions are not Installed."

![List the policies and fixes](images/vs_code4.png "List the policies and fixes")

You can learn more about the policy by selecting “View Problem” or select “Quick Fix” to do exactly that. By selecting “Apply fix for - Ensure Virtual Machine Extensions are not Installed” you automatically patched your codebase for a common misconfiguration.

![Remediation lines added automatically](images/vs_code5.png "Remediation lines added automatically")

Now you can commit that code to your repository with the patch and improved posture.

**Now that we know what Bridgecrew is scanning for and what the results look like, let’s automate it!**