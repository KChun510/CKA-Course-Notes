# Kublets
- A pod can be run indep, from KUBE API server, via a kubelet. 

## Manual set up ( Creation of static pods )
- Can point Kubelets to read from a pod def file/ container def files.
- So that at node/ kubelet boot, it pulls the pod meta data by itself.
- Set in "pod manifest" field. 
    - Or in config field.
- Or set manually in the yaml file. 

### To list these pods.
- Use `docker ps`, not conencted to kube api server 

## Kubelet
- Can intake information/ metadata from external sorces.
    - Direct file paths.
    - Also can make `http` req to the kube api server.


### Diff between static pods and DaemonSets
- Static pods:
    - Deploy control plane comps as static pods

- DaemonSets:
    - Good for deploying clients/ agents. 



