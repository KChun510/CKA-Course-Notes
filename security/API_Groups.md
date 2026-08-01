# API Groups
- Central around the `kube-api server`
- If we wanted to cehck the api version.
    - `curl https://<api_ip/name>/version`

## Focus on two endpoints `/api` and `/apis`
- Core `/api`
    - Namespaces, events, bindings, pods, configmaps, secrets, etc.

- Named `/apis`
    - `/apps`
        - `/v1`
            - `/deployments`
            - `/replicasets`
            -  etc.

- TLDR, two ways of accessing resources via the API. The named `/apis` use another layer of sorting.


## Access
- You can do classic `curl` request
- Or you can use `kubectl Proxy`
    - On all of your following curl request, the kuebctl proxy will append your certs defined in your `.config` file.
