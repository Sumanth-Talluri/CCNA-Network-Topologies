# OPEN SHORTEST PATH FIRST (OSPF)

## OSPF

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/8.%20OSPF/screenshots/simpleOSPF.png" width="70%">

### Commands

In Router 0 :

```console
Router(config)#router ospf ?
<1-65535> Process ID
Router(config)#router ospf 1
Router(config-router)#network 192.168.1.0 ?
A.B.C.D OSPF wild card bits
Router(config-router)#network 192.168.1.0 0.0.0.255 area 0
Router(config-router)#network 192.168.2.0 0.0.0.255 area 0
Router(config-router)#
```

In Router 1 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.2.0 0.0.0.255 area 0
Router(config-router)#network 192.168.3.0 0.0.0.255 area 0
Router(config-router)#
```

&nbsp;

## OSPF between 4 Routers

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/8.%20OSPF/screenshots/4router.png" width="90%">

### Commands

In Router 0 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
Router(config-router)#
```

In Router 1 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
```

In Router 2 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
```

In Router 3 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
```

&nbsp;

## Multi-Area OSPF

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/8.%20OSPF/screenshots/image--067.png" width="90%">

### Commands

In Router 0 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
Router(config-router)#
```

In Router 1 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
Router(config-router)#
```

In Router 2 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
Router(config-router)#
```

In Router 3 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
Router(config-router)#
```

Similarly Configuring Router 6 & 7 that is in ‘Area 1’ :

```console
Router(config)#router ospf 1
Router(config-router)#network 10.0.0.0 0.255.255.255 area 1
Router(config-router)#
```

Similarly Configuring Router 8 & 9 that is in ‘Area 2’ :

```console
Router(config)#router ospf 1
Router(config-router)#network 172.16.0.0 0.0.255.255 area 2
Router(config-router)#
```

In Router 4 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
Router(config-router)# network 172.16.0.0 0.0.255.255 area 2
Router(config-router)#
```

In Router 5 :

```console
Router(config)#router ospf 1
Router(config-router)#network 192.168.0.0 0.0.255.255 area 0
Router(config-router)# network 10.0.0.0 0.255.255.255 area 1
```
