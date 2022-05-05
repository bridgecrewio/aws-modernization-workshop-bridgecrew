---
title: "Optional local Setup"
chapter: false
weight: 8
pre: "<b>2.5 </b>"
---

### Go it alone (Local setup)


This option is strongly discouraged as we will be unable to provide the same level of support throughout the live workshops. Every local environment is different and we cannot guarantee that these instructions will work flawlessly in every environment.


However, we’d like to provide this so that you can see the steps needed to install in the interest of transparency for what has been configured behind the scenes in the two automated workshop environments above, the following steps give example commands for installing all the needed dependencies for the workshop.


These stepsThey are intended foraimed at a Linux X64 Ubuntu 20.04 machine, as our automated workshop environments run in cContainers on these OS images.


#### Docker / PodMan / Rancher Desktop / ContainerD


    Your machine must be able to  will need a machine capable of running containers., The our examples below all use Ddocker Ddesktop in order to spin up containerized dependencies, buthowever all dependencies should work with other local ContainerD-based container tooling.  \
 \
See this page to install Docker Desktop. For docker desktop install, see here: [https://docs.docker.com/desktop/](https://docs.docker.com/desktop/)


#### Install the KIND CLI tool


```
    curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.1/kind-linux-amd64
    chmod +x ./kind
    mv ./kind /usr/bin/kind
```


### Build theour KIND Kubernetes cluster


```
    /usr/bin/kind create cluster --name bridgecrew-workshop
```


### Install the Kkubectl CLI tool


```
    curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
    chmod +x ./kubectl
    mv ./kubectl /usr/bin/kubectl
```


### Set up a ‘pipenv’ for our Python dependencies.


This is optional, but is a and good practice for compartmentalizing Ppython dependencies and libraries from each other when you’re on a system where you may be working with multiple projects. In this example, we’ll be installing our Checkov.io scanning tool into the pipenv, but you can alsocould just as well install Ccheckov globally with `pip install checkov` instead.


```
    apt install -y pipenv
    pipenv --python 3.8
```


### Install Bridgecrews’ Checkov.io scanning tool


```
    pipenv install checkov || pip install checkov
```


	

### Install Bridgecrews’ Yor.io infrastructure tag and trace tool


```
    docker pull bridgecrew/yor
```


### Clone the “KustomizeGoat” sample repository


```
    git clone https://github.com/bridgecrewio/kustomizegoat.git
```



### Test your installed dependencies


If all of the dependencies are correctly installed, the following commands should all run withoutsuccessfully, displaying no errors or failures:


```
    kubectl cluster-info --context kind-bridgecrew-workshop
    checkov --version
    docker run --tty --volume /root:/root bridgecrew/yor --version
    cd kustomizegoat && git status
```
