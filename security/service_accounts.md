# Service Acccounts
- Used for machines/ 3rd party interaction
- I.e: Monitoring

# User Accounts
- I.e: Admin account

## Tokens and accounts
- When a kubernete cluster is set up
    - All namespaces have a service account called `default`

- When pod is created
    - `default` sa auto binds to the pod.

## Workflow
- SA, work as gateways into resources 
- For each SA, there is a token created with it automatically. 

- Alternative:
    - If you just want to make `rest` api calls to the resource itself.
    - You can just pass along the token in the API call. 
