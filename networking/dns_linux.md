# Hostfiles
- Assihing IPs to a domain name, locally
    - Linux, `/etc/hosts`

- How to post a host to a DNS server? 
    - loc: `/etc/resolv.conf`
        - nameserver <DNS-IP>
        

# Oder of search? Host file or DNS? 
- loc: `nsswitch.conf`

# nslookup
- Get host metadata

# dig

# CoreDNS
- DNS server solution
    - Helps manage hostname to IP mappings from one place
    - Can use `/etc/hosts` as a source for records
    - Runs on port `53` by default

# CoreDNS workflow
- Download CoreDNS
```bash
curl -LO https://github.com/coredns/coredns/releases/download/v1.12.4/coredns_1.12.4_linux_amd64.tgz
```

- Extract the binary
```bash
tar -zxf coredns_1.12.4_linux_amd64.tgz
```

- Add DNS entries on the DNS server
    - loc: `/etc/hosts`
    - Example:
```bash
10.0.0.10 web
10.0.0.11 db
```

- Create CoreDNS config
    - loc: `Corefile`
    - Use the `hosts` plugin to read `/etc/hosts`
```conf
.:53 {
    hosts /etc/hosts {
        reload 1m
        fallthrough
    }

    forward . /etc/resolv.conf {
       max_concurrent 1000
    }
    cache 30
    log
    errors
}
```

- Start CoreDNS
```bash
./coredns
```

- Point hosts to the DNS server
    - loc: `/etc/resolv.conf`
```bash
nameserver <DNS-IP>
```

- CoreDNS has plugins
    - Kubernetes uses the CoreDNS kubernetes plugin
    - Kubernetes DNS spec: https://github.com/kubernetes/dns/blob/master/docs/specification.md
    - CoreDNS kubernetes plugin: https://coredns.io/plugins/kubernetes/
