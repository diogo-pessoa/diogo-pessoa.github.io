+++
draft = false
date = "2024-06-01"
title = "kubectl context usage"
description = "Preparation for CKA exam - notes with kubectl config and context commands"
slug = "kubectl-context-usage"
authors = ["Diogo Pessoa"]
tags = ["kubernetes", "cka", "kubectl"]
categories = ["notes"]
+++

# Summary

k8s kubectl context configuration and usage.

{{<toc>}}

## use-context

```
kubectl config use-context kubernetes-admin@kubernetes
```

## setting current context namespace

```
kubectl config set-context --current --namespace=application1
```

```bash
# Show Merged kubeconfig settings.
kubectl config view 

# use multiple kubeconfig files 
#at the same time and view merged config
KUBECONFIG=~/.kube/config:~/.kube/kubconfig
```

## config view password

```bash
# get the password for the e2e user
kubectl config view \
-o jsonpath='{.users[?(@.name == "e2e")].user.password}'
```

## config view certificate for e2e User

```bash
# get the certificate for the user user
kubectl config view --raw \
-o jsonpath='{.users[?(.name == 'user')].user.client-certificate-data}'\
| base64 -d
```

## config get users

### display the first user

```bash kubectl config view -o jsonpath='{.users[].name}'```

### list users

```bash kubectl config view -o jsonpath='{.users[*].name}' ```


## References

* [Authenticating Across Clusters with kubeconfig](https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/)
* [kubectl config](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#config)