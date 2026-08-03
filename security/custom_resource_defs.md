# Deployments:
- What controls, the actions taken during a deployment?
    - The `Controller` evals the deploymetn config.
        - Sees if any changes, and applys config.
        - I.e: If there are three replicas, it deployes the 3, with the given def.

# Main point:
- We have a custom resource
    - It has a custom spec, that gets stored in the etcd server

- We then have to define our own controller.
    - That intakes the yaml/ evaluates ETCD entries.
    - In this example.
        - The custom controller, intakes the params from the `flightTicket` object.
        - creates a pod, books the ticket via an API, then deletes the pod.

## Custom Resource Definitions (CRD):
- Look at docs for this, standard yaml format for def
    - Your resource gets defined into a group -> then a kind.
    - You can narrow this reousece to certain scopes.
    - 
