# Defining what can be done, once access attained
- I.e: DO you want every user, with the abilty to take down nodes, pods, or resources? No.

## Access methods

- `Node Authorizer`
    - Built in logic/ group based auth
- `ABAC`/ External access
    - Attribute based access
        - i.e:
            - dev-user: {"kind": can view pods, delete, etc}
- `RBAC`:
    - Creating a role with a defined set of perms
    - Then can associate/ add users to those roles.
- `Webhook`:
    - Managing access through external/ 3rd party tools.
    - Tools: `Open Policy Agent`
- `AlwaysAllow` and `AlwaysDeny`

## Where do we set these? 
- `execStart=/usr/local/bin/kube-apiserver ... ... ... --authorization-mode=Node, RBAC, Webhook`
