# Traffic
- TLDR: Going over basic fundamentals

## Kubernetes default:
- `All Allow Rule`
    - By default all pods, and nodes can reach each other. (Ingress + Egress)

## Network Pol:
- Link a network pol, between one or more pods.
    - I.e: Define ports that are open, per pods


## Yaml def:
- Using names and labels, to selct the resoureces that you want to apply the policy to. 
- Then create a new yaml resource, where you can define ingress and egress traffic, + ports.

