# Kube Proxy

## POD Network
- Whithin a cluster, every pod can reach every other pod. ( Like docker network , but pod scale)
- No gaurentee that the `POD IP` will stay static
    - Solution, create a `named service`.
        - Pod can be reached by service name, or by allocated static IP.
        - A virtual comp, that lives in kubernetes mem. 

## Proxy
- Runs on each node in cluster
- Each time new service is created
    - Creates the proper rules/ populates an `IP table` in memory.

