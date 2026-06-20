# Docker Vs Container D

## Docker
- Beginging of container erra, docker was one of the first.

## Problem needed to allow other container runtimes to be orchrastrated by kubernetes.
- Solution, *CRI (Contianer Runtime Interface)*
    - Any vendor could be a container runtime as long as they followed the OCI (open container intitiave) standards
- OCI, standards are comprised of two parts.
1) Imagespec
2) runtimespec
- As long as any container meets these standards, they can be orchrastred using the CRI.

### Docker is now seperted from containerD.
- You build containers using docker.
- Then run with containerD

## ContainerD commands, quick overview
`ctr images pull docker....`
`ctr run etc`
- Better used for debugging containerD

## A better tool is *nerdctl* - cli tool (Nerd Control Tool)

## *crictl*, tool/ interaction from the kubernetes community
- Used to debug and inspect container runtimes.
- Is aware of indiv pods can use `crictl pods`





