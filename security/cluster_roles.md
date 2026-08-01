# Cluster Role Bindings
- Roles and role bindings are `namespaced`

## Namespaces:
- Great for isolating resources.
- Pods, jobs, replicasets, etc

## Or alternative `Cluster Scoped`.
- nodes, PV, clusterroles, namespaces

### Full-list:
`kuebctl api-resouces --namespaces ...`

# Cluster Roles 
- I.e:
- Cluster Admin
    - Can view Nodes
    - Can create Nodes
    - Can delete Nodes

- Storage Admin
    - can view PVs
    - can create PVs
    - can delete PVCs

## Workflow
- Another yaml def

```yaml
apiVersion: rbac....
kind: ClusterRole
metedata:
    name: cluster-admin
rules:
- apiGroups: [""]
  resources: ["nodes"] 
  verbs: ["list", "get", "create", "delete"]
        ````
