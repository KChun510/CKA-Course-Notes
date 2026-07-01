# Resource Request
- Each container/ pod, has  two fields `mem` and `cpu`.
- Used as values to determine which node best fits for scheduling.

# Resource limits
- Pod def, limits section. Same two fieds

# Pod exceeding the specified limit? 
- Pods get throttled, CPU wise. 
- However with memory, there is no limit. Will lead to `Out of memory kill`.
    - Pod get terminated.

## Problem:
- A pod can sufficate/ hog resources of other pods.

### CPU Allocation

#### The most ideal set up, in terms of `Request & limits`
- Request, and no limits. ( Most ideal )
- Request and limits. (Second ideal)

### Memory Allocation
- Requests, and no limits. ( Most ideal, but dangerous )
- Request + limits. ( Second most ideal )


# LimitRange ( Namespace scoping for resources ), budget per container.
- A new yaml def, where you can define the rousource limits on a namespace.
- Enforced when a pod is created, prior pods are not effected.

# Resource Quota, Cap on entire namespace
- Limit the allocation within an entire cluster. 
- Setting hard limits
