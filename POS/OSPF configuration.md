## Configure OSPF on router
```bash
R1(config-router)#router ospf 1
R1(config-router)#network <network-ip> <wildcard-mask> area 0
```

Mask /24 is written as 255.255.255.0, the wildcard mask is then 0.0.0.255
- For each octet, compute how much to 255

## Check neighbors
```bash
R1#show ip ospf neighbor
```