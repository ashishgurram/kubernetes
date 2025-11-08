
# Minikube and kubectl

## Table of Contents
1. [Minikube](#minikube)
2. [kubectl](#kubectl)

## Introduction
This document covers the basics of Minikube for local Kubernetes clusters and the kubectl tool for cluster management.

# minikube
![alt text](../images/image-7.png)
- docker would be pre installed
- it runs using a virtual box
- it creates a virtual box and the node runs in that
- its a 1 node k8s cluster for testing and you can run multiple nodes for master etc to test

# kubectl
- to interact with the node that we have in minikube we need a way to communicate with , we use kubectl for that.
- ![alt text](../images/image-9.png)
- kubectl si ont just for minikube we use for even cloud as well


> TO install minikube on mac just do brew install minikube
>
> install docker desktop
> 
> do `minikube start` to start the node

```
ashishgurram@Ashishs-MacBook-Pro ~ % kubectl get nodes
NAME       STATUS   ROLES           AGE   VERSION
minikube   Ready    control-plane   22s   v1.34.0
ashishgurram@Ashishs-MacBook-Pro ~ % minikube status
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

ashishgurram@Ashishs-MacBook-Pro ~ % kubectl version
```
