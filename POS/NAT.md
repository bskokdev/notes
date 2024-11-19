## Tell the router which interface is which
```bash
# This is the inside (private facing) interface
R1(config)#int fa0/0
R1(config-if)#ip nat inside

R1(config)#int fa0/1
R1(config-if)#ip nat outside

R1(config)#ip nat pool <POOL_NAME> <PUB_IP> <PUB_IP> mask
R1(config)#ip nat inside source list 1 <POOL_NAME> overload
R1(config)#access-list 1 permit <PRIVATE_NETWORK_IP> <wildcard>
```