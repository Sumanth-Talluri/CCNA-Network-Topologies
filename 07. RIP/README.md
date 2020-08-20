# ROUTING INFORMATION PROTOCOL (RIP)

## RIP

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/07.%20RIP/screenshots/rip.png" width="70%">

### Commands

In Router 0 :

```console
Router(config)#router rip
Router(config-router)#network 192.168.1.0
Router(config-router)#network 192.168.3.0
Router(config-router)#exit
Router(config)#
```

In Router 1 :

```console
Router(config)#router rip
Router(config-router)#network 192.168.2.0
Router(config-router)#network 192.168.3.0
Router(config-router)#exit
Router(config)#
```

&nbsp;

## RIP between 3 Routers

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/07.%20RIP/screenshots/rip3routers.png" width="90%">

### Commands

In Router 0 :

```console
Router(config)#router rip
Router(config-router)#network 192.168.1.0
Router(config-router)#network 192.168.4.0
Router(config-router)#exit
Router(config)#
```

In Router 1 :

```console
Router(config)#router rip
Router(config-router)#network 192.168.2.0
Router(config-router)#network 192.168.4.0
Router(config-router)#network 192.168.5.0
Router(config-router)#exit
Router(config)#
```

In Router 2 :

```console
Router(config)#router rip
Router(config-router)#network 192.168.3.0
Router(config-router)#network 192.168.5.0
Router(config-router)#exit
Router(config)#
```

&nbsp;

## RIP LOAD BALANCING

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/07.%20RIP/screenshots/loadbalancing.png" width="90%">

### Commands

Checking the routing table of Router 3 :

```console
Router#show ip route
Gateway of last resort is not set
C 192.168.1.0/24 is directly connected, FastEthernet1/0
R 192.168.2.0/24 [120/2] via 192.168.3.2, 00:00:04, FastEthernet0/0
[120/2] via 192.168.4.2, 00:00:25, FastEthernet0/1
C 192.168.3.0/24 is directly connected, FastEthernet0/0
C 192.168.4.0/24 is directly connected, FastEthernet0/1
R 192.168.5.0/24 [120/1] via 192.168.3.2, 00:00:04, FastEthernet0/0
R 192.168.6.0/24 [120/1] via 192.168.4.2, 00:00:25, Fast Ethernet0/1
Router#
```

&nbsp;

Tracing the path from 192.168.1.2 to 192.168.2.2

&nbsp;

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/07.%20RIP/screenshots/tracert.png" width="50%">
