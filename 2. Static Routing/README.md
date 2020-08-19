# Static Routing

## Static Routing between 2 Routers

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/2.%20Static%20Routing/screenshots/staticrouting.png" width="90%">

### Commands

In Router 0 :

```console
Router(config)#ip route 192.168.3.0 255.255.255.0 192.168.5.2
Router(config)#ip route 192.168.4.0 255.255.255.0 192.168.5.2
```

In Router 1 :

```console
Router(config)#ip route 192.168.1.0 255.255.255.0 192.168.5.1
Router(config)#ip route 192.168.2.0 255.255.255.0 192.168.5.1
```

&nbsp;

## Static Routing between 3 Routers

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/2.%20Static%20Routing/screenshots/3routers.png" width="90%">

### Commands

In Router 0 :

```console
Router(config)#ip route 192.168.2.0 255.255.255.0 192.168.4.2
Router(config)#ip route 192.168.3.0 255.255.255.0 192.168.4.2
Router(config)#ip route 192.168.5.0 255.255.255.0 192.168.4.2
Router(config)#exit
Router#show ip route
Gateway of last resort is not set
C 192.168.1.0/24 is directly connected, FastEthernet0/0
S 192.168.2.0/24 [1/0] via 192.168.4.2
S 192.168.3.0/24 [1/0] via 192.168.4.2
C 192.168.4.0/24 is directly connected, FastEthernet0/1
S 192.168.5.0/24 [1/0] via 192.168.4.2
Router#
```

In Router 1 :

```console
Router(config)#ip route 192.168.1.0 255.255.255.0 192.168.4.1
Router(config)#ip route 192.168.3.0 255.255.255.0 192.168.5.2
Router(config)#exit
Router#show ip route
Gateway of last resort is not set
S 192.168.1.0/24 [1/0] via 192.168.4.1
C 192.168.2.0/24 is directly connected, FastEthernet0/0
S 192.168.3.0/24 [1/0] via 192.168.5.2
C 192.168.4.0/24 is directly connected, FastEthernet0/1
C 192.168.5.0/24 is directly connected, FastEthernet1/0
Router#
```

In Router 2 :

```console
Router(config)#ip route 192.168.1.0 255.255.255.0 192.168.5.1
Router(config)#ip route 192.168.2.0 255.255.255.0 192.168.5.1
Router(config)#ip route 192.168.4.0 255.255.255.0 192.168.5.1
Router(config)#exit
Router#show ip route
Gateway of last resort is not set
S 192.168.1.0/24 [1/0] via 192.168.5.1
S 192.168.2.0/24 [1/0] via 192.168.5.1
C 192.168.3.0/24 is directly connected, FastEthernet0/0
S 192.168.4.0/24 [1/0] via 192.168.5.1
C 192.168.5.0/24 is directly connected, FastEthernet0/1
Router#
```
