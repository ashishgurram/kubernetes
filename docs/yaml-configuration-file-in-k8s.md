 
# YAML Configuration File in Kubernetes

## Table of Contents
1. [Parts of a Kubernetes Config File](#3-parts-of-a-kubernetes-config-file)
2. [Format of Configuration File](#format-of-configuration-file)
3. [Blueprint for Pods (Template)](#blueprint-for-pods-template)
4. [Connecting Services to Deployments and Pods](#connecting-services-to-deployments-and-pods-label--selector--port)

## Introduction
This document explains the structure and best practices for writing YAML configuration files in Kubernetes, including metadata, specification, and service connections.
## 3 parts of a Kubernetes config file 
- (metadata, specification, status(its added by k8s(it comes from etcd)))
## format of configuration file
  - Yaml configuration
  - its very strict about indentation
  - its very std
  - can use yaml validtor to fix
  - Store the ocnfig file with your code(IAAC)
## blueprint for pods (template)
  - Deployment manges pods
  - template has its own metadata and spec section
  - it applies to pod
  - and this is blueprint for a pod
    - port, image , name etc
## connecting services to deployments and pods (label & selector & port)
- connections is established using labels and connectors
- metadata of the yaml contains the labels
- And spec part contains the selectors
- labels
  - They have any key value pair for the component
  - Pods get the label through the template blueprint
  - This label is matched by the selctor

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 2
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.16
        ports:
        - containerPort: 8080
```

```
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080

```
![alt text](images/k8s-yaml-structure.png)
