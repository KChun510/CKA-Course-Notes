# Rollout and Versioning
- A deploymeny triggers a `Rollout`/ version
    - Help keep track of version, and rollback
- `Kubectl rollout status deployment/<dep-nam>`

## Deployment strategy
- Destroy 5 curr, then deploy 5 new.
    - Prob: Rolling, can destroy and isntate one  new deployment one by one.

- Rollout strategy is default
    - When using kubectl command.

- `kubectl rollout undo deployment <dep-name>`
    - To get back to last dep version
