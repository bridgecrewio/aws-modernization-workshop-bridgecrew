---
title: "Optional local setup"
chapter: false
weight: 8
pre: "<b>2.5 </b>"
---

### Go it alone (local setup)

This option is strongly discouraged because we will be unable to provide the same level of support throughout the live workshops. Every local environment is different and  we cannot guarantee that these instructions will work flawlessly in every environment.

However, we’d like to provide this option so that you can see the steps needed to install all the needed dependencies for the workshop.

These steps are intended for a Linux X64 Ubuntu 20.04 machine, as our automated workshop environments run in containers on these OS images.

#### Docker / PodMan / Rancher Desktop / ContainerD

Your machine must be able to run containers. The examples below all use Docker Desktop to spin up containerized dependencies, but all dependencies should work with other local ContainerD-based container tooling.  

See [this page](https://docs.docker.com/desktop/) to install Docker Desktop.


#### Install the kind CLI tool


```
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.1/kind-linux-amd64
chmod +x ./kind
mv ./kind /usr/bin/kind
```


### Build the kind Kubernetes cluster


```
/usr/bin/kind create cluster --name bridgecrew-workshop
```


### Install the Kubectl CLI tool


```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x ./kubectl
mv ./kubectl /usr/bin/kubectl
```


### Optional: Set up a ‘pipenv’ for our Python dependencies.


This is an optional step, but good practice for compartmentalizing Python dependencies and libraries from each other when you’re on a system where you may be working with multiple projects. In this example, we’ll be installing our Checkov scanning tool into the pipenv, but you can also just as well install Checkov globally with `pip install checkov` instead.


```
apt install -y pipenv
pipenv --python 3.8
```


### Install Checkov, Bridgecrew's open source scanning tool


```
pipenv install checkov || pip install checkov
```


	

### Install Yor, Bridgecrew's IaC tag and trace tool


```
docker pull bridgecrew/yor
```


### Clone the KustomizeGoat sample repository


```
git clone https://github.com/bridgecrewio/kustomizegoat.git
```



### Test your installed dependencies


If all of the dependencies are correctly installed, the following commands should all run without errors or failures:

```
kubectl cluster-info --context kind-bridgecrew-workshop
checkov --version
docker run --tty --volume /root:/root bridgecrew/yor --version
cd kustomizegoat && git status
```
