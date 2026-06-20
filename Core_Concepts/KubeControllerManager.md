# Kube Controller Manager 
- The offices of the ship.
- Continuously monitors the state of the system, and adjusting to the desired directive.

## Node controller
- Responsible for monitoring status of nodes, and takes the neccary actions to keep the application running.

- Checks `status` of nodes every 5s. 
    - If not recieving a `heartbeat` from a node, after 40 secdons. 
        - Marked unreachable.

    - If `unreachable` after 5 mins, POD is evicted. And replaced. ( if part of replica set )


## Replication Controller
- Sets the # of replicated pods.

# All of these comps + more, gets packaged into the `kube-controller-manager`





