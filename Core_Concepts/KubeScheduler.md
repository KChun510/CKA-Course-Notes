# Kube Scheduler
- Only responsiblity: Dictate which pod, belongs to which node.
    - I.e: Which crates/containers belong to which ship.

- Can assign based on variois requiremnts.
    - Mem and CPU reqs.

- Sorting phase:
    - Filter out all nodes that do not meet reqs.
    - Finaly, evaluate which node would have the most recourses after alloction. Then choose.

## Pod creation:
- The Kubelet, within the node creates the pod.
