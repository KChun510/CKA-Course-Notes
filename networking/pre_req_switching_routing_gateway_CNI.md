# Basics
- Switch, connectes devices whithin a network.
    - You bind ips to ports with a interface

- To reach other networks, you use routers
    - Via a switch, you can add a route
        - I.e: Designate a route defining that you can reach x network via y ip. 

- Connecting router to the internet.
    - You can say, for any `request` that doesnt know to route to. 
        - You can designate a default gateway
            - I.e: Your internet gateway.

# Linux default
- Packets are not forwarded by default
    - So if you ping a machine, you wont recieve a response.
    - need to declare forwarding
`cat /proc/sys/net/ipv4/ip_forward`
    - Setting it to 1, will forward
    - Plus need to set in /etc file, for persitant changes
    
