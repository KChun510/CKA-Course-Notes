# Using a PVC within a pod
- Once a `Persistent Volume Claim (PVC)` has been created, referance it within the pod definition.
    - Define the PVC under the `volumes` section.
    - Set `claimName` to the name of the existing PVC.
    - Mount that volume within the container using `volumeMounts`.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: mypod
spec:
  containers:
    - name: myfrontend
      image: nginx
      volumeMounts:
        - mountPath: /var/www/html
          name: mypd
  volumes:
    - name: mypd
      persistentVolumeClaim:
        claimName: myclaim
```

## ReplicaSets and Deployments
- The same configuration can be used for a ReplicaSet or Deployment.
    - Add the `volumeMounts` and `volumes` sections to the resource's pod template.

## Reference
- [Configure a Pod to use a PersistentVolumeClaim](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#claims-as-volumes)
