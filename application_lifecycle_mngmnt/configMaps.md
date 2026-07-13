# Congfig maps.

- Pass config data, in KV pairs, injecting into the pods.
1) create config map
2) inject

## Def:
- imparative:
    - `kubectl create configmap <config-name> --from-literal=<key>=<value>`
    - `kubectl create configmap --from-file=app_config.properties`

- declareative:
    - `kubectl create -f config-map.yaml`
    - Creating a set of pre defined defs, for your pods.

## Configuring with a pod:
- In pod def file, define new prop:
    - `envFrom`:
        - `configMapRef`:
            `name`: <app-name>

- Can also use a seperate `volume`
    - Maybe for example SSL/ Certbot automation?
