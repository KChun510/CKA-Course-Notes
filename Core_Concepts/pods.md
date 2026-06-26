# Assumptions
- App is already conainerized
- The kubernetes cluster is already set up and working
    - Single or mutli node setup

# POD
- A single instanace of an appliction (i.e: Our zotplug stack would be a single pod.)

## Use case
- What if load on application becomes to large? 
- Then you can always deploy new additional pods. 

````md
# Basic Kubernetes Structure Commands

Kubernetes objects usually build on each other like this:

Node → Pod → ReplicaSet → Deployment → Service

A **Pod** is the smallest deployable unit in Kubernetes.  
A **Deployment** manages Pods and keeps the desired number running.  
A **Service** exposes Pods inside or outside the cluster.

---

## Cluster Info

```bash
kubectl cluster-info
````

Shows basic information about the Kubernetes control plane.

```bash
kubectl get nodes
```

Lists worker/control-plane nodes in the cluster.

```bash
kubectl get namespaces
```

Lists namespaces in the cluster.

---

## Pods

Create a simple Pod:

```bash
kubectl run nginx --image=nginx
```

List Pods:

```bash
kubectl get pods
```

List Pods with more detail:

```bash
kubectl get pods -o wide
```

Describe a Pod:

```bash
kubectl describe pod nginx
```

View Pod logs:

```bash
kubectl logs nginx
```

Delete a Pod:

```bash
kubectl delete pod nginx
```

---

## Deployments

Create a Deployment:

```bash
kubectl create deployment nginx-deploy --image=nginx
```

List Deployments:

```bash
kubectl get deployments
```

List ReplicaSets created by Deployments:

```bash
kubectl get replicasets
```

Scale a Deployment:

```bash
kubectl scale deployment nginx-deploy --replicas=3
```

Check the rollout status:

```bash
kubectl rollout status deployment nginx-deploy
```

Update the image:

```bash
kubectl set image deployment/nginx-deploy nginx=nginx:1.25
```

Undo a rollout:

```bash
kubectl rollout undo deployment nginx-deploy
```

Delete a Deployment:

```bash
kubectl delete deployment nginx-deploy
```

---

## Services

Expose a Deployment inside the cluster:

```bash
kubectl expose deployment nginx-deploy --port=80 --target-port=80
```

List Services:

```bash
kubectl get services
```

Short version:

```bash
kubectl get svc
```

Describe a Service:

```bash
kubectl describe service nginx-deploy
```

Delete a Service:

```bash
kubectl delete service nginx-deploy
```

---

## Namespaces

Create a namespace:

```bash
kubectl create namespace dev
```

Run a Pod in a namespace:

```bash
kubectl run nginx --image=nginx -n dev
```

Get Pods from a namespace:

```bash
kubectl get pods -n dev
```

Get Pods from all namespaces:

```bash
kubectl get pods -A
```

Delete a namespace:

```bash
kubectl delete namespace dev
```

---

## YAML Output / Dry Run

Generate YAML without creating the object:

```bash
kubectl run nginx --image=nginx --dry-run=client -o yaml
```

Save generated YAML to a file:

```bash
kubectl run nginx --image=nginx --dry-run=client -o yaml > pod.yaml
```

Apply a YAML file:

```bash
kubectl apply -f pod.yaml
```

Delete resources from a YAML file:

```bash
kubectl delete -f pod.yaml
```

---

## Useful Shortcuts

```bash
kubectl get po
kubectl get deploy
kubectl get rs
kubectl get svc
kubectl get ns
```

Common abbreviations:

| Full Object | Short Name |
| ----------- | ---------- |
| pods        | po         |
| deployments | deploy     |
| replicasets | rs         |
| services    | svc        |
| namespaces  | ns         |
| nodes       | no         |

---

## Quick Mental Model

```text
Deployment
   ↓ creates
ReplicaSet
   ↓ creates
Pods
   ↓ selected by
Service
```

Example:

```bash
kubectl create deployment web --image=nginx
kubectl scale deployment web --replicas=3
kubectl expose deployment web --port=80
kubectl get pods
kubectl get deploy
kubectl get rs
kubectl get svc
```

```

One CKA note: get comfortable using `--dry-run=client -o yaml`. That is one of the most useful exam habits because you can generate manifests quickly instead of writing everything from scratch.
```

