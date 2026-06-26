# Two boys with same first name 
- Differentiate via lastname

- Each house has their own set of rules/ and resources. 

## The seperate houses refer to namespaces
- default namespace, created on kubernetes boot 
    - Self needing services ( Kube-system, kube-public, default )

## Same cluster for dev and prod?
- You can seperate them via their own `namespace`
- Can define quota and certain amount.
- Resouces in a namespace, can  referance each other via their name/ first name. 
    - You can reach other pods, in antother namespace, append the namespace to the name of the pod. 


View Namespaces

List all namespaces:

kubectl get namespaces

Short form:

kubectl get ns
View Resources in the Default Namespace

If no namespace is specified, Kubernetes uses the default namespace.

kubectl get pods
kubectl get deployments
kubectl get services
View Resources in a Specific Namespace

Use --namespace or -n.

kubectl get pods --namespace=dev
kubectl get pods -n dev
kubectl get pods --namespace=prod
kubectl get pods -n prod
Create a Namespace
kubectl create namespace dev
kubectl create namespace prod

Short form:

kubectl create ns dev
Create Resources in a Specific Namespace

Create a deployment in the dev namespace:

kubectl create deployment nginx --image=nginx --namespace=dev

Short form:

kubectl create deployment nginx --image=nginx -n dev
Apply YAML to a Specific Namespace
kubectl apply -f deployment.yaml --namespace=dev

Short form:

kubectl apply -f deployment.yaml -n dev
Delete a Namespace

Deleting a namespace deletes all resources inside it.

kubectl delete namespace dev

Short form:

kubectl delete ns dev
Switch Default Namespace for Current Context

Instead of typing -n dev every time, set the default namespace for the current context:

kubectl config set-context --current --namespace=dev

Now this command:

kubectl get pods

will show pods from the dev namespace by default.

Switch Back to Default Namespace
kubectl config set-context --current --namespace=default
Check Current Context and Namespace
kubectl config view --minify

Or check the current context:

kubectl config current-context
Common Namespace Examples

Get pods in dev:

kubectl get pods -n dev

Get pods in prod:

kubectl get pods -n prod

Get services in dev:

kubectl get svc -n dev

Get deployments in prod:

kubectl get deploy -n prod

Describe a pod in a namespace:

kubectl describe pod <pod-name> -n dev

Delete a pod in a namespace:

kubectl delete pod <pod-name> -n dev
CKA Tip

For the exam, -n is faster than typing --namespace.

Example:

kubectl get pods -n dev

is the same as:

kubectl get pods --namespace=dev
Mental Model
kubectl get pods

means:

Show pods in the current/default namespace.
kubectl get pods -n dev

means:

Show pods in the dev namespace.
kubectl config set-context --current --namespace=dev

means:

Make dev the default namespace for future kubectl commands.


