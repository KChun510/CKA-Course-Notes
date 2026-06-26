# Groups seperating each service 
- Allow connections/ comms to our microservices in our cluster. 

## Use cases:
- Can listen to port on a node, and foward the traffic.

## Service Types: 
- NodePort
- ClusterIP ( Creates a virt. IP within the cluster )
- LoadBalancer 

### NodePort - service
- External access to an application
    - Mapping ports from node to pod.
        - Port on Pod ( Target Port )
        - Port on the service itself ( Port )
        - Port on the node itself ( NodePort )

### Creating a service
```yaml
apiVersion: v1 
kind: Service
metadata: 
    name: .....

spec:
    type: NodePort
    ports:
    - targetPort: 80 (is an array, can have mult mappings per service)
      port: 80
      nodeport: 30008
    selector: 
        - ( list of labels from pod def, links service to pod )
```

#### Side case/ extra features of NodePort.
- Lets say you have mult pods under same labels.  The nodePort selector will randomly distribute/ forward request to sepereate pods. ( Built in load balaner )

- Will do the same with nodes themselves.

- Crazy
