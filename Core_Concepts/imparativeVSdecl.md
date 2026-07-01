# Two approaches

## Imperative
- Would take a taxi, and tell what and how to do.

### Examples:
- Prov. VM.
- Install NGINX server
- Edit nginx conf, etc.

## Declarative
- Uber, just specficy the final desitination.
- System, figures out how by itself.

### Examples:
- Simple yaml, that declars what you want done.
- Typical InfAsCode pattern.

## In the kubernetes world.

### Imperative:
````md
# Kubernetes Imperative Commands

## Create a Pod

```bash
kubectl run --image=nginx nginx
````

## Create a Deployment

```bash
kubectl create deployment --image=nginx nginx
```

## Expose a Deployment

```bash
kubectl expose deployment nginx --port 80
```

## Edit a Deployment

```bash
kubectl edit deployment nginx
```

## Scale a Deployment

```bash
kubectl scale deployment nginx --replicas=5
```

## Update Deployment Image

```bash
kubectl set image deployment nginx nginx=nginx:1.18
```

## Create Resource From YAML

```bash
kubectl create -f nginx.yaml
```

## Replace Resource From YAML

```bash
kubectl replace -f nginx.yaml
```

## Delete Resource From YAML

```bash
kubectl delete -f nginx.yaml
```

### Declarative:
```bash
kubectl apply -f <file_name>
```


# Manifest/ Object Files:
````md
# Kubernetes Imperative Object Configuration Files

## Create Objects

Create Kubernetes objects from a YAML configuration file.

```bash
kubectl create -f nginx.yaml
````

## Update Objects

Edit an existing Kubernetes object directly.

```bash
kubectl edit pod myapp-pod
```

## Example Pod Configuration File

```yaml
apiVersion: v1
kind: Pod

metadata:
  name: myapp-pod
  labels:
    app: myapp
    type: front-end

spec:
  containers:
    - name: nginx-container
      image: nginx
```

## Kubernetes Stored Object Example
````md
# Kubernetes Imperative Object Configuration Files

## Create Objects

Create Kubernetes objects from a YAML configuration file.

```bash
kubectl create -f nginx.yaml
````

## Update Objects

Edit an existing Kubernetes object directly.

```bash
kubectl edit pod myapp-pod
```

## Example Pod Configuration File

```yaml
apiVersion: v1
kind: Pod

metadata:
  name: myapp-pod
  labels:
    app: myapp
    type: front-end

spec:
  containers:
    - name: nginx-container
      image: nginx
```

## Kubernetes Stored Object Example

Kubernetes stores extra runtime information in memory, such as object status.

```yaml
apiVersion: v1
kind: Pod

metadata:
  name: myapp-pod
  labels:
    app: myapp
    type: front-end

spec:
  containers:
    - name: nginx-container
      image: nginx

status:
  conditions:
    - lastProbeTime: null
      status: "True"
      type: Initialized
```

# Declarative ( Better/ Sick features )


````md
# Kubernetes Declarative Commands

## Create Objects

Create or update Kubernetes objects from a YAML file.

```bash
kubectl apply -f nginx.yaml
````

Apply all configuration files from a directory.

```bash
kubectl apply -f /path/to/config-files
```

## Update Objects

Update existing Kubernetes objects by applying the modified YAML file again.

```bash
kubectl apply -f nginx.yaml
```

## Example Pod Configuration File

```yaml
apiVersion: v1
kind: Pod

metadata:
  name: myapp-pod
  labels:
    app: myapp
    type: front-end-service

spec:
  containers:
    - name: nginx-container
      image: nginx:1.18
```

## Key Idea

Declarative management means you define the desired state in YAML, then let Kubernetes create or update the object to match that state.

```bash
kubectl apply -f <file-name>.yaml
```

