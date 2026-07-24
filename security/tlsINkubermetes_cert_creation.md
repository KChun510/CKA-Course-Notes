# Tools
- EasyRSA, OPENSSL, CFSSL

## Certificate Authority (CA)
- `openssl genrsa -out ca.key 2048`
    - Generate private key
- `openssl req -new -key ca.key -subg "/CN=KUBERNETES-CA" -out ca.csr`
    - Request/generate a private key/ crt, not yet signed
    - `CN` = Common name
- `openssl x509 -req -in ca.csr -signkey ca.key -out ca.crt`
    - Sign the given crt

## Certs for ADMIN User
- `openssl genrsa -out admin.key 2048`
    - Generate key
- `openssl req -new -key admin.key -subj "/CN=KUBERNETES-admin" -out admin.csr`
    - Cert Sign Request
- `openssl x509 -req -in admin.csr -CA ca.crt -CAkey ca.key -out admin.crt`
    - Sign cert

- !Add group details whithin the `CERT`!
    - This is how you differentiate users from each other.
    - You can ADD `group details` with -ou parameter. 
    - `openssl req -new -key admin.key -subj "/CN=KUBERNETES-admin/OU=system:masters" -out admin.csr`

## Rest of server side certs
- Follow same process.

# Now how do you use these certs?
- Option One: You can curl an API/ resource and pass in certs manually into the request.
- Option Two ( The better option ):
    - Use a `kube-config.yaml` file.
        - You can set the crt location from whitin the file.


## KubeAPI Server
- Why does this process differ from rest?
    - The kubeAPI server is the most accessed module/ resouce.
        - All server side kubernetes comps, go through the API server
        - Plus every single client interacts with the server.
        - !Main point: People refer the the KubeAPI via many differnet names!.
            - I.e: 
                - kubernetes
                - kubernetes.default
                - kubernetes.default.svc
                - 10.96.0.1
                - 172.17.0.87
                - etc.
        - To stress the point, you need to pass in a `openssl.cnf` file to account for the multiple "valid" domain names.

- `openssl genrsa -out apiserver.key 2048`
    - Generate private key

- `openssl req -new -key apiserver.key -subj "/CN=kube-apiserver" -out apiserver.csr -config openssl.cnf`
    - Create a signing request, for all custom names/ ips
    - Passed in `openssl.cnf`

Example `openssl.cnf`:
```bash
        [req]
        req_extension=fds
        ...
        ...
        [v3_req]
        ...
        [alt_names]
        DNS.1 = kubernetes
        DNS.2 = kubernetes.default

        DNS.3 = kubernetes.default.svc
        DNS.4 = "..."
        IP.1 = 10.96.0.1
        IP.2 = 172.17..
```
- `openssl x509 -req -in apiserver.csr -CA ca.crt -CAkey ca.key -CAcreateserial -out apiserver.crt -extensions v3_req -extfile openssl.cnf -days 1000`
    - Generate your crt


## Finally how do you init these crts, into the `Kube-api server`
- `ExecStart=/usr/local/bin/kube-apiserver.... \\ ... \\ <command args to pass in crts, keys, and pem>`

# Each node in the cluster, has a kubelet ( HTTP server )
- kubelet needs TLS encruption.
- Once key pair made for the singular kubelet
    - You can point to CAfile via the Kubelet yaml.

## What names do you assign to these certs?
- Kubernetes standard for nodes
 - `system:node:nodeXX`
    - xx = integer from 01 - 99S
- Also must have group info applied
    - `Group: Systemnodes`



