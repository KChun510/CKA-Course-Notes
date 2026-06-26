# Pods with YAML
- Similar to docker compose yaml files.

## Basic yaml definitions
- Gaurenteed 4 fields:
1) apiVersion
    - Version of the Kubernetes API

2) kind
    - Type of object were tyring to create
        - Other kinds
            - Pod, service, replicatset, deployment
3) metadata
    - name: name of app
    - labels:
        (any other kv pair)
        app: myapp
        type: front-end

4) spec:
    containers: (can be an array of containers, mult containers can be in a single pod)
        - name: nginx-container
          image: nginx
