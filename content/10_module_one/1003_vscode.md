---
title: "VSCode Plugin"
chapter: true
weight: 103
pre: "<b>4.3 </b>"
---

## Aid development with VSCode plugins

The Bridgecrew CLI can be used for a quick local scan, but is better suited when automated into a CI/CD pipeline, which we'll dive into in Module Two.

For more developer-friendly local scanning, the Bridgecrew Checkov VSCode plugin shows the scan results directly at the point of code, without having to constantly re-run the CLI tool, and with the results annotated directly onto the specific code block causing the violation.

![Bridgecrew VSCode demo](./images/checkov-vscode-demo.gif "Bridgecrew VSCode demo")

You can find the plugin [on Github, here](https://github.com/bridgecrewio/checkov-vscode) or search `Checkov by Bridgecrew` within VSCode extensions.