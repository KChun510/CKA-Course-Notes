# Problem
- When you store secrets, in kubernetes.
    - They are just base64 encodings of the strings.
        - That can be viewed, and de-hashed.

## Focus on this video
- Secrets are stored on the kube controller `etcd` server, `in plane text ( not encypted. )`

## Solution
- Enable `encryption at rest` for `etcd`
    - There is docs on kubernetes.

### General approach
- Create a seperate config file
    - with `encryption at rest` option set
    - set file is designated location/ pass into kubernetes
- Good to go.
