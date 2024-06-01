+++
draft = false
date = "2024-06-01"
title = "Querying Kubernetes Metadata"
description = "Preparation for CKA exam - Querying Kubernetes Metadata"
slug = "cka-metadata"
authors = ["Diogo Pessoa"]
tags = ["kubernetes", "cka"]
categories = ["notes"]
+++

{{<toc>}}

## Summary

Collection of commands to query resource metadata in kubernetes.

### Sorting  resources by creation timestamp

```bash
  k get pod -A --sort-by=.metadata.creationTimestamp
```

#### All namespaces

`--all-namespaces` or `kubectl -A`

#### List pods Sorted by Restart Count

```bash
kubectl get pods --sort-by='.status.containerStatuses[0].restartCount' 
```

#### List Services Sorted by Name

```bash 
kubectl get services --sort-by='.metadata.name'
```


#### List PersistentVolumes sorted by capacity

```bash
kubectl get pv --sort-by=.spec.capacity.storage
```