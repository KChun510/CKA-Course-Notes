# Eqauting "rooms" to namespaces
- Going over `scope` in terms of namespaces and hosts.
- A hosts, can be the auth figure of household. 
    - While each namespace is a subor. that has there own space. 
    - but hosts can see everytign

## Creating a network NS
- `ip netns add res`
    - `ip netns exec red ip link`
- `ip netns`
- `ip link`
    - listing interfaces

### Why?  
- Using namespaces, limits scope to the hosts interface/ namespace

## Want to let namespaces comm with each other? 
- You can define a route/ interfaces from whitin the namespaces. 
    - i.e:
        1) Create `veth  (virtual ethernet)` connections from namespace to namespace
            - Define veths, for each namesapce
                `ip link add veth-red type veth peer naem veth-blue`
                - Creating the `veth`
            - Attach each interfcae to the aprop namespace
                `ip link set veth-red netns red`
                `ip link set veth-blue netns blue`
        2) assign ips to namespaces
        3) start up veth on namespaces
        `ip -n red link set veth-red up`

## What happens when you have a bunch of namespaces? 
- Create a virtual switch whithin a hosts.
- There are many apps, we using `linux bridge`
    - `ip link add v-net-0 type bridge`

## Take-away
- On any critical system. 
    - Namespace desgin/ config is crucial for secuity.
