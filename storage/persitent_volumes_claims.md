# Claiming a volume, from the avail pool
- Similar in nature to taints and tolerances.

## Concept
- When defining your persitent vols. you define a set of limits.
    - I.e: Perms, read, write, copy, and capacity.
        - Your users whithin the cluster, can then define a `Persitent Volume Claim ( PVC )`. 
        - The claim, defines what there looking for perms + storage.
            - Kubernetes will then eval their request, and allocate them a volume/ chunk of a volume if it meets vols. def.
    
