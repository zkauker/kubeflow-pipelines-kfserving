# kubeflow-pipelines-kfserving
Install kubeflow pipelines in GCP with knative and kfserving integration

## Prerequisites
You can use Google Cloud Shell or a local workstation to complete these steps

## Set up command-line tools
You'll need the following tools in your development environment. If you are using Cloud Shell, these tools are installed in your environment by default.
* gcloud
* kubectl
* git

Clone repository
```git clone https://github.com/mtaufikromdony/kubeflow-pipelines-kfserving.git```
 
In the repository describe with 3 files :
* k8s-kubeflow-install.sh : in this file will configure parameter to deploy new GKE cluster and install kubeflow pipelines
* Kfserving-install.sh : in this file will start installing istio as container network, knative, cert manager as prerequisite for kfserving installation
* Uninstall.sh: to uninstall kubeflow pipelines from GKE cluster and will delete the cluster
 
``` cd kubeflow-pipelines-kfserving/ ```
``` chmod +x *.sh ```
 
## Create new GKE cluster with kubeflow pipelines
```./k8s-kubeflow-install.sh ```
 
## Use an existing GKE cluster with installed Kubeflow pipelines

In order to use an existing cluster the `kubectl` CLI should be properly authenticated. This can be done with the `gcloud` CLI tool as follows:

`gcloud container clusters get-credentials <your cluster's name>`

## Install KFserving and sklearn test
``` ./kfserving-install.sh ```
 
## Uninstall kubeflow pipelines and delete GKE cluster
``` ./uninstall.sh ```
