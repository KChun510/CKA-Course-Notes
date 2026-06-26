# Rolling updates
- Upgrade application containers. 
    - New version of app?
        - Slowly rollout new versions/ replacing old pods with new version itetivly.
    
    - Rollbacks:
        - Need to recover from a failed deployment?
            - Undo prev iterative steps


## Creating a deployment
- Using typlical .yml format.
    - i.e: apiVersion, kind, metadata, etc.

- Diff: The kind,is set to `Deployment`
- Rest of Markup is exactly the replicaset defintion. 



