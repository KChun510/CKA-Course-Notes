# Authorization
- Typically the workflow with kubernetes
- kubelet -> Authentication -> Authoriztion -> Create Pod

- Authentication/ Authorazation process when interacting with the kube api. 

## Roles and Resources:
- Restricting access to user rols ( Role Based Access Control/ RBAC ).

# Admission Controllers
- Help us enforce how the cluster is used.

## Pre-Built:
- AlwaysPullimages
- DefaultStorageClass
- EventRateLimit
- NamespaceExists
    - Want to create a pod in namespace `blue` which does not exist. 
        - Request gets denied, from first going through this admission controller.
    - Can set option/ controller to create namespace if doesnt exisit.
        - `NameSpaceAutoProvision`.
- etc

## Adding a admission controller:
- Update the `kube-apiserver`  manifest/ file. ( Actualy yaml file )



