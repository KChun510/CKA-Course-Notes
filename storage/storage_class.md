# When creating PV's or even using cloud based
- The worflow is `static provishined`
    - You have to manually define each pv and PVC, not dynamic

# Solution: 
- You no longer need to manually define PV's.

## Using GCP:
1) Create a `Storage Class` def
    - Containing the proper yaml to connect to GCP Instance
2) Now, any user/ resource can define a PVC referancing the `Storage Class`
3) GCP will auto allocate a persitant volume + bind to resource. 
