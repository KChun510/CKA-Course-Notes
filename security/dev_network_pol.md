# Summary
- Due to the simple arc being shown ( 1 pod = 1 service = 1 container).
    - Networking arch/ dev, follows a similar workflow to setting up docker networks.

- Key point.
    - Create a `kind: NetworkPolicy`, yaml file.
    - Using `podselectors`, to declare the pods you want to apply the policy to.
        - Then define ports + ingress/egress rule, to declare the pods you want to apply the policy to.
            - Then define ports + ingress/egress rules.

## What if you want to apply policys, to specfic namespaces?
- Other wise, would apply to all namespaces, scanning for any pod with matchin label.

- `namespaceSelector: \ matchLabels: \ kubernetes....`

## What if we had an external backup server, seperate from  the kubernetes cluster?
- You can configure policys, that allow traffic from known IP addresses.
- `ipBlock:
    cidr: <external-ip>/port`
