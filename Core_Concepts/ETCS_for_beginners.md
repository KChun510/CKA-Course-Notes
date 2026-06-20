# What is etcd?
- A distributed reliable key value store.
- Kuberneted database/ source of truth.
- It stores things like:
`Pods
Deployments
Services
ConfigMaps
Secrets
Namespaces
Node info
Cluster state`
- Can be used seperatly from kubernetes, as its own indepedant KV store.

## Basic type of operations:

## Basic etcd Commands
```bash
# Use etcd API v3
export ETCDCTL_API=3

# Check health
etcdctl endpoint health

# Create key-value pairs
etcdctl put /app/config/port 8080
etcdctl put /app/config/env dev
etcdctl put /app/config/debug true

# Read one key
etcdctl get /app/config/port

# Read only the value
etcdctl get /app/config/port --print-value-only

# Read all config keys
etcdctl get /app/config/ --prefix

# List only keys
etcdctl get /app/config/ --prefix --keys-only

# Update a key
etcdctl put /app/config/port 9090

# Watch a key for changes
etcdctl watch /app/config/port

# Delete one key
etcdctl del /app/config/debug

# Delete all keys under a prefix
etcdctl del /app/config/ --prefix
```


