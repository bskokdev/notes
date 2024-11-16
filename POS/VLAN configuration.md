We need to first assign IPs on the PCs

## Create VLANs and assign name
```bash
Switch>enable
Switch#conf t
Switch(config)#vlan <vlan-number>
Switch(config-vlan)#name <vlan-name>
```

## Assign SW interfaces to VLANs
```bash
Switch>enable
Switch#conf t
Switch(config)#int <int-number>
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan <vlan-number>
```

### We can also use interface range
```bash
Switch(config-if)#int range fa0/1-4
Switch(config-if-range)#switchport mode access
```

### Assign trunk interface
```bash
Switch(config)#int <int-number>
Switch(config)#switchport mode trunk
```

### Allow only some VLANs on a trunk
```bash
Switch(config)#int <int-number>
Switch(config)#switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan add <ID>
```

If we transfer multiple VLANs via a single router port, we need to create logical interfaces

## Create logical VLAN interfaces on router
- Do this only if there's more than 1 VLAN to be routed, otherwise use normal interface
```bash
Router>enable
Router#conf t

Router(config)#int <interface-number>
Router(config-if)#no shutdown

Router(config-if)#int <interface-number>.<vlan-number>
For example: Router(config-if)#int fa0/0.10

Router(config-subif)#encapsulation dot1q <vlan-number>
Router(config-subif)#ip add <IP> <MASK>
```