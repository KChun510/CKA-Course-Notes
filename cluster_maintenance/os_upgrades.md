# Summary
- Lets say you need to take down a node for maintenance. I.e: OS Upgrade.

- If you take down a node, and default time 5 mins/3600s the kube controller would consider that pod dead and apply its default workflows.

## Solution:
- Rather than bringing a node down, instead drains it of all pods ( Drain command ).
    - Pushing all pods whithin onto other valid nodes.


- Once your done with maintencae. Use the `uncordon`  command. "Un-drain"/ allow pods to be schedulded onto node again.
