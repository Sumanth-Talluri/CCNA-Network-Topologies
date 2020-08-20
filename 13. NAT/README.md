# NETWORK ADDRESS TRANSLATION (NAT)

## NAT I

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/13.%20NAT/screenshots/nat1.png" width="90%">

### Commands

In Router 0 :

```console
Router#conf t
Router(config)#access-list 1 permit 192.168.1.0 0.0.0.255
Router(config)#ip nat inside source list 1 interface fa0/1
Router(config)#int fa0/1
Router(config-if)#ip nat outside
Router(config-if)#int fa0/0
Router(config-if)#ip nat inside
Router(config-if)#
Router#
```

&nbsp;

## NAT II

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/13.%20NAT/screenshots/nat2.png" width="90%">

### Commands

In SSN College Router (Router0) :

```console
Router#conf t
Router(config)#access-list 1 permit 192.168.1.0 0.0.0.255
Router(config)#ip nat inside source list 1 interface fa0/0
Router(config)#int fa0/0
Router(config-if)#ip nat outside
Router(config-if)#int fa0/1
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#ip route 70.1.1.0 255.255.255.0 200.1.1.2
Router(config)#
```

Now accessing Google webpage from SSN College’s 192.168.1.2 PC:

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/13.%20NAT/screenshots/nat2-res1.png" width="50%">

&nbsp;

In SRM College Router (Router1) :

```console
Router#conf t
Router(config)#access-list 1 permit 192.168.1.0 0.0.0.255
Router(config)#ip nat pool SRM 100.1.1.4 100.1.1.7 netmask 255.255.255.252
Router(config)#ip nat inside source list 1 pool SRM
Router(config)#int fa0/0
Router(config-if)#ip nat outside
Router(config-if)#int fa0/1
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#ip route 70.1.1.0 255.255.255.0 100.1.1.2
Router(config)#
```

Now accessing Google webpage from SRM College’s 192.168.1.2 PC:

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/13.%20NAT/screenshots/nat2-res2.png" width="50%">

&nbsp;

## NAT III

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/13.%20NAT/screenshots/nat3.png" width="90%">

### Commands

In SSN College Router (Router0) :

```console
Router>en
Router#conf t
Router(config)#access-list 1 permit 192.168.1.0 0.0.0.255
Router(config)#ip nat inside source list 1 interface fa0/0
Router(config)#int fa0/0
Router(config-if)#ip nat outside
Router(config-if)#int fa0/1
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#ip route 0.0.0.0 0.0.0.0 200.1.1.2
Router(config)#exit
Router#
```

&nbsp;

In SRM College Router (Router1) :

```console
Router#conf t
Router(config)#access-list 1 permit 192.168.1.0 0.0.0.255
Router(config)#ip nat inside source list 1 interface fa0/0
Router(config)#int fa0/0
Router(config-if)#ip nat outside
Router(config-if)#int fa0/1
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#ip route 0.0.0.0 0.0.0.0 100.1.1.2
Router(config)#
```

&nbsp;

In Google Router (Router3) :

```console
Router#conf t
Router(config)#ip nat inside source static 192.168.1.2 74.125.224.72
Router(config)#int fa0/0
Router(config-if)#ip nat outside
Router(config-if)#int fa0/1
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#ip route 0.0.0.0 0.0.0.0 199.1.1.1
Router(config)#
```

&nbsp;

In Facebook Router (Router4) :

```console
Router#conf t
Router(config)#ip nat inside source static 192.168.1.2 69.171.247.21
Router(config)#int fa0/0
Router(config-if)#ip nat outside
Router(config-if)#exit
Router(config)#int fa0/1
Router(config-if)#ip nat inside
Router(config-if)#exit
Router(config)#ip route 0.0.0.0 0.0.0.0 70.1.1.1
Router(config)#exit
Router#
```

&nbsp;

<p>
<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/13.%20NAT/screenshots/nat3-res1.png" width="45%">
<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/13.%20NAT/screenshots/nat3-res2.png" width="45%">
</p>
&nbsp;
