# INTERNET PROTOCOL - VERSION 6 (IPV6)

## STATIC ROUTING IN IPV6

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/15.%20IPV6/screenshots/ipv6.png" width="90%">

### Commands

In Router 0 :

```console
Router(config)#ipv6 unicast-routing
Router(config)#int fa0/0
Router(config-if)#ipv6 address 2001:1::1/64
Router(config-if)#no shutdown
Router(config-if)#int fa0/1
Router(config-if)#ipv6 address 2001:2::1/64
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#ipv6 route 2001:3::/64 2001:2::2
```

&nbsp;

In Router 1 :

```console
Router(config)#ipv6 unicast-routing
Router(config)#int fa0/0
Router(config-if)#ipv6 address 2001:3::1/64
Router(config-if)#no shutdown
Router(config-if)#int fa0/1
Router(config-if)#ipv6 address 2001:2::2/64
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#ipv6 route 2001:1::/64 2001:2::1
```

&nbsp;

## Dynamic Routing in IPV6

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/15.%20IPV6/screenshots/ipv6-dynamic.png" width="90%">

### Commands

#### RIP-NG(Routing Information Protocol – Next Generation)

In Router 0 :

```console
Router(config)#ipv6 router rip NetworkGeek
Router(config-rtr)#exit
Router(config)#int fa0/0
Router(config-if)#ipv6 rip NetworkGeek enable
Router(config-if)#int fa0/1
Router(config-if)#ipv6 rip NetworkGeek enable
Router(config-if)#exit
```

&nbsp;

In Router 1 :

```console
Router(config)#ipv6 router rip NetworkGeek
Router(config-rtr)#exit
Router(config)#int fa0/0
Router(config-if)#ipv6 rip NetworkGeek enable
Router(config-if)#int fa0/1
Router(config-if)#ipv6 rip NetworkGeek enable
Router(config-if)#exit
```

&nbsp;

#### OSPF v3

In Router 0 :

```console
Router(config)#ipv6 router ospf 1
%OSPFv3-4-NORTRID: OSPFv3 process 1 could not pick a router-id,please configure manually
Router(config-rtr)#router-id 1.1.1.1
Router(config-rtr)#exit
Router(config)#int fa0/0
Router(config-if)#ipv6 ospf 1 area 0
Router(config-if)#int fa0/1
Router(config-if)#ipv6 ospf 1 area 0
Router(config-if)#
```

&nbsp;

In Router 1 :

```console
Router(config)#ipv6 router ospf 1
%OSPFv3-4-NORTRID: OSPFv3 process 1 could not pick a router-id,please configure manually
Router(config-rtr)#router-id 2.2.2.2
Router(config-rtr)#exit
Router(config)#int fa0/0
Router(config-if)#ipv6 ospf 1 area 0
Router(config-if)#int fa0/1
Router(config-if)#ipv6 ospf 1 area 0
Router(config-if)#
```

&nbsp;

#### EIGRP

In Router 0 :

```console
Router(config)#ipv6 router eigrp 1
Router(config-rtr)#eigrp router-id 1.1.1.1
Router(config-rtr)#no shut
Router(config-rtr)#exit
Router(config)#int fa0/0
Router(config-if)#ipv6 eigrp 1
Router(config-if)#int fa0/1
Router(config-if)#ipv6 eigrp 1
Router(config-if)#
```

&nbsp;

In Router 1 :

```console
Router(config)#ipv6 router eigrp 1
Router(config-rtr)#eigrp router-id 2.2.2.2
Router(config-rtr)#no shut
Router(config-rtr)#exit
Router(config)#int fa0/0
Router(config-if)#ipv6 eigrp 1
Router(config-if)#int fa0/1
Router(config-if)#ipv6 eigrp 1
Router(config-if)#
```

&nbsp;

## ACL in IPV6

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/15.%20IPV6/screenshots/ipv6.png" width="90%">

### Commands

In Router 0 :

```console
Router(config)#ipv6 access-list NetworkGeek
Router(config-ipv6-acl)#deny ipv6 host 2001:1::2 host 2001:3::2
Router(config-ipv6-acl)#permit ipv6 any any
Router(config-ipv6-acl)#exit
Router(config)#do show access-list
IPv6 access list NetworkGeek
deny ipv6 host 2001:1::2 host 2001:3::2
permit ipv6 any any
Router(config)#int fa0/0
Router(config-if)#ipv6 traffic-filter NetworkGeek in
Router(config-if)#
```
