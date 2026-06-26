# Replication Controller
- If pod crashes, you can set N instances of a pod running at once.

## Other use cases
- Load balacing and Scaling
    - When the number of users increases, you can launch additional pods across the cluster.

## Repliaction Controller Vs ReplicaSet
- Replicset is the new recommnded way.
- Replication Controller is a bit older.

## Basic Yaml definition ( Using `RepliactionController` )

```yml
apiVersion: v1
kind: ReplicationController
metadata:
    name: myapp-rc
    labels:
spec:
    template ( Defining the pod template ):
        (move all contents of a pod def into this tempate section)

replicas: 3
```

## Basic Yaml definition ( Using `Replica Set` )
```yml
apiVersion: apps/v1
kind: ReplicaSet
metedata:
    name: myapp-replicaset
    labels:
        app: myapp
        type: front-end

spec:
    template:
        (move all contents of a pod def into this tempate section)
replicas: 3
selector: (Identify which pods you need to be replicated.)
    (Utilizes labels for indentification)
    matchLabels:
        type: front-end

```


