## Enable RIP and set version to 2
```bash
Router>enable
Router>#conf t

Router(config)#router rip
Router(config-router)#version 2
```

## Add all connected networks
```bash
Router(config)#network <IP>
Router(config)#network <IP>
Router(config)#no auto-summary
```

## Exclude interface from RIP updates
```bash
Router(config)#passive-interface <interface>
```