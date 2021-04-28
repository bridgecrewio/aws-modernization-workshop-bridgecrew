---
title: "Bridgecrew Setup"
chapter: false
weight: 13
pre: "<b>3.2 </b>"
---

You’ll need to sign up for a free Bridgecrew account to follow along with this tutorial. You can sign up for a free account [here](https://bridgecrew.cloud/?utm_source=awsworkshop).

![Signup to Bridgecrew](./images/signup_bridgecrew.png)

## Checkov CLI
In this tutorial, we’re also going to use Checkov CLI. The CLI works on Windows, Mac, and Linux. You can install it with pip:

```bash
pip3 install bridgecrew
```

If installing globally on your system (not in a python venv or pipenv) you may need to have permissions to write the libraries to the necessary locations, ie:

```bash
sudo pip3 install bridgecrew
```

If you run into problems, try the [alternate install instructions](https://docs.bridgecrew.io/docs/ingesting-scan-data#installation?utm_source=awsworkshop).


## Bridgecrew API token

Throughout the tutorial, you’ll need to use the Bridgecrew API token. You can access [it here](https://www.bridgecrew.cloud/integrations/api-token) or in your Bridgecrew account by navigating to the Integrations tab and selecting API Token.

![Bridgecrew API token](./images/bc_api_key.gif)
