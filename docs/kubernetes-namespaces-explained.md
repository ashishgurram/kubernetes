# Kubernetes Namespaces explained

## What is a Namespace
- Organise resources in namespaces
- virtual cluster inside a k8s cluster
- When you create a cluster there are 4 default namespaces created
  - kube-system:  
    - Do not create or modify in kube-system
    - System processes
    - Master and kubectl processes
  - kube-public
    - publicaly accessible data
    - a ConfigMap which contains cluster information
    - `kubectl cluster-info`
  - kube-node-lease
    - recent addition
    - headrbeats of nodes
    - each node has associated lease object in namespace
    - Determines the node availability
  - default
    - resources youc reate are located here (but ofc you can add new namespaces)
    - `kubectl create namespace my-namespace`
    - Create a namespace with a configuration file
  ## Why to use namespaces

  1. Everything in one namespace
     1. clutered
     2. and no overview
     3. complicated to maintain
     4. Conflicts: many teams, same application
     5. Resource sharing: stagin and evelopment(reuse the common resource)
     6. For blue/green deployment: the version will be different and need to use same resources and they can resuse the common resources
     7. Acess and resroucr limts on namespaces(based on teams)
     8. Can keep limits CPu, RAM, storage per NS.
  2. Resource grouped in namespace
  1. ![alt text](images/namespaces-overview.png)

  ## Characteristics of Namespaces?
  1. you cant access most of the resrouces from another namespace
     1. Each NS must define their own COnfigMap and secrets
     2. Service can be shared 
  2. Componente which cant be created within a namespace
     1. live globally in a cluster
     2. you cant isolate them
     3. example: volume and node
        1. list component not bound to namespsace: `kubectl api-resources --namespaced=false`
        2. Vice versa: `kubectl api-resources --namespaced=true`

## create a component in a namespace
- by default, components are given with default namespace
- all the kubectl cmd take namespace as argument if not given its default by default.
- `kubectl apply -f mysql-configmap.yaml --namespace=my-namespace`
- we can also just add the namespace in metadata like `namespace: my-namespace` it will automaticalt apply it to that particular namespace
- its better to do the second way
- Change aCtive namespace
  - kubens is the tool used to do that. install using bre
  - `kubens my-namsepace` cmd will set the active namespace
