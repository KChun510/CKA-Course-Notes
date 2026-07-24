# Server Certs
- Public keys
- Private keys

# Client Certs
- Same as server, but generated client side.

# Cluster ( Master & Worker Nodes ):
- All traffic between nodes, must be encrypted/ secured.

## Server Certs
- Kube-apiserver
    - Generate their own key pair.
- etcd server
    - Generate their own key pair.
- kubelet server
    - ...

## Client Certs
- Admin user
    - Neesd a key pair.
- Scheduler
    - Client that access the kube API server.
    - Needs a key pair.
- KubeController-manager
    - ...
- Kube-proxy:
    - ...

