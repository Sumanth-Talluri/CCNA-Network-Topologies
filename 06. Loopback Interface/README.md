# Loopback Interface

## Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/06.%20Loopback%20Interface/screenshots/loopback.png" width="80%">

## Commands


In Router 0 :

```console
Router(config)#int fa0/0
Router(config-if)#ip address 192.168.1.1 255.255.255.0
Router(config-if)#exit
Router(config)#int loopback ?
<0-2147483647> Loopback interface number
Router(config)#int loopback 0
Router(config-if)#ip address 192.168.2.1 255.255.255.0
Router(config-if)#int loopback 1
Router(config-if)#ip address 192.168.4.1 255.255.255.0
Router(config-if)#int loopback 2
Router(config-if)#ip address 192.168.6.1 255.255.255.0
Router(config-if)#exit
Router(config)#
```

In Router 1 :

```console
Router(config)#int fa0/0
Router(config-if)#ip address 192.168.1.2 255.255.255.0
Router(config-if)#int loopback 0
Router(config-if)#ip address 192.168.3.1 255.255.255.0
Router(config-if)#int loopback 1
Router(config-if)#ip address 192.168.5.1 255.255.255.0
Router(config-if)#int loopback 2
Router(config-if)#ip address 192.168.7.1 255.255.255.0
```
