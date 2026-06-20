# Kube API server
- There are two forms of interacting with the *Master Node*/ *control pane*.
1) Is the `kubectl` cli tool, which can be used to interact with the API.
2) Or you can make request to the API direclty.

## Authorization:
- Any request before making it to the API, gets authenticated then validated. 

### The schedular:
- MOnitors the API server, and sees a new pod. 
- The schedular identiefes the right node to place pod, and then passes that information to the kube-api server to update the etcd cluster.

### Then ifnoramtion gets passed to the `kubelet`
- creates the pod on the node.
- Uopdats the status back to the API server.

# Key: `KubeAPIserver` is the focal point between each process.
- Ping a comp, return status to KubeAPI Server, update ETCD, then pass along to kubelet, finally pass result back to KubeAPI..., update ETCD, repeat.
