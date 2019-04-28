---
description: This page describes how to deploy PM415 on Google Cloud using Kubernetes
---

# Kubernetes

## Create a Kubernetes cluster

1. Login to Google Cloud and choose navigate to **Kubernetes Engine**
2. Choose **Create cluster**
3. Choose **Standard cluster** and accept all the defaults
4. Click **Create**

## Create a kubectl config

1. Install **kubectl** using [these instructions](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
2. Return to the Kubernetes Engine and click edit icon - it's a little pencil:

   ![](../.gitbook/assets/kubernetes-engine-pm415-google-cloud-platform-2019-04-27-18-19-20%20%281%29.png)

3. Write down the endpoint IP address.
4. Click **Show credentials** and copy the certificate to your clipboard
5. In a terminal - convert the key to base64 - the following works on a mac: `pbpaste | base64`
6. return to the cluster credential window and copy the admin password
7. Create a file named `config.yml` with the following contents:

```text
kind: Config
apiVersion: v1

clusters:
- cluster:
    server: https://(paste the endpoint IP address)
    certificate-authority-data: (paste the base64 cert here)
 name: default

current-context: default
contexts:
- context:
    cluster: default
    namespace: default
    user: default
  name: default

users:
- name: default
  user:
    username: admin
    password: (paste the admin password here)
```

## Test your config

1. Create the `KUBECONFIG` environment variable to reference your config: `export KUBECONFIG=$PWD/config.yml`
2. Test your config `kubectl get node`

This should return the list of Kubernetes nodes in your Google Cloud account.

```text

NAME                                                STATUS    ROLES     AGE       VERSION
gke-standard-cluster-1-444   Ready     <none>    22m       v1.11.8-gke.6
gke-standard-cluster-1-445   Ready     <none>    23m       v1.11.8-gke.6
gke-standard-cluster-1-446   Ready     <none>    23m       v1.11.8-gke.6
```

