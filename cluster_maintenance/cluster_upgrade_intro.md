# Cluster Upgrade Introduction
- `KubeAPI server` - is the central comp of kubernetes.
- All other comps must be <= Vers. of `KubeAPI server`

## What does this allow?
- Because were allowed to have comps, at different versions.
- We are allowed to update `indiv comps`.
    - Allowing isolation, without bricking infra.

## When should you update? 
- Only supports up to `3 prev minor versions`
- Use this window to determine when to update

## How should you upadte? 
- You should update, one minor version at a time.
- First master nodes, then worker nodes.
    - All workloads on worker nodes, if master nodes down, will still continue
    - But will be locked out of `kubectl` mngmt commands.

## Cloud features
- GCP, allows one click upgrades avail ( IF deployed on GCP ).

# Strategys for worker node upgrades
1) Upgrade all.
2) Upgrade one node at a time.
3) Add new nodes to the cluster, nodes with newer versions!
    - Easy on a cloud env.
    - Move workload to the new node, and remove old node.

# Kubeadm features
- `Kubeadm upgrade plan`
    - Will list most stable version
        - The current versions of your cluster/ comps

## Kubeadm commands
- `apt-get upgrade -y kubeadm=1.12.0-00`
    - First need to upgrade kubeadm, before you can update rest of cluster.
- `kubeadm upgrade apply v1.12.0`
    - Upgrading your cluster
- `kubectl get nodes`
    - Kubelets whithin each node, have not been updated.
    - Must indep, upgrade those.
- `apt-get upgrade -y kubelet=1.12.0-00`
....Find rest of commands on manual process on docs lol


