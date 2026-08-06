# Like docker volumes but on a pod level
- Need to create a volume within the pod.
- Containers, then need to also referance that internally defined volume.
- Laslty, point internal pod volume to external volume.
    - Via: `hostpath: <path_name>`

## Not best used for a multi node cluster ^
- There are public cloud solutions.
    - AWS, GCP, Etc.
