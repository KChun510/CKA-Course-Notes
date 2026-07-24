# Vert Pod Autoscaling

## VPA does not come built in:
- We must deploy it! ( Can grab yaml file, from official kubernetes github )

### Comps of the VPA
- VPA Recommender::
    - Intakes metrics, from metrics server
        - Creates resource suggestions.

- VPA Updater: 
    - Detects pods with sub opt. resources, it evicts them.

- VPA admission controller:
    - Uses recs from admission controller, to create new pods 
        - when pod is killed: It intervenes and updates resouces based on given recs.


