## Enable IPv6 routing on a router
```bash
R1(config)#ipv6 unicast-routing
```

## Add an IPv6 address to an interface
```bash
R1(config)#int fa0/0
R1(config-if)#ipv6 address <IPv6 address>/64 eui-64
```

# IPv6 RIP (RIPng)
```bash
R1(config)#ipv6 unicast-routing
R1(config)#int fa0/0

# creates the RIPng process and enables RIPng on the interface

R1(config-if)#ipv6 address <IPv6 address>/64 eui-64
R1(config-if)#ipv6 rip <rip-process-name> enable
R1(config-if)#no shutdown
```

# IPv6 OSPF (OSPFv3)
```bash
R1(config)#ipv6 unicast-routing
R1(config)#ipv6 router ospf <process-id> (1)
R1(config)#router-id <1.1.1.1> (has to be unique for each router)

R1(config)#int fa0/0
R1(config-if)#ipv6 add <IP>/64 eui-64
R1(config-if)#ipv6 ospf <process-id> area 0
R1(config-if)#no shutdown
```
