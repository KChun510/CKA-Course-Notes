# Backup canidates
- Resource Config
    - Pods, deployments, etc.
- Etcd Cluster
- Pers. Vols.

## Sols.
- Git

### Best way
- Query the `KubeAPI` server
    - kuebctl get all --all-namespcaes -o yaml > <file-name>.yaml

### Getting a snapshot of your etcd cluster.
- etcdctl snapshot save snapshot.db

