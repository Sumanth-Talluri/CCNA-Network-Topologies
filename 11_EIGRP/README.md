# Enhanced Interior Gateway Routing Protocol (EIGRP)

## EIGRP

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/11.%20EIGRP/screenshots/eigrp.png" width="60%">

### Commands

In Router 0 :

```console
Router#conf t
Router(config)#router eigrp ?
<1-65535> Autonomous system number
Router(config)#router eigrp 1
Router(config-router)#network 192.168.1.0 ?
A.B.C.D EIGRP wild card bits
<cr>
Router(config-router)#network 192.168.1.0 0.0.0.255
Router(config-router)#network 192.168.2.0 0.0.0.255
Router(config-router)#
```

In Router 1 :

```console
Router#conf t
Router(config)#router eigrp 1
Router(config-router)#network 192.168.0.0 0.0.255.255
Router(config-router)#
```

&nbsp;

## EIGRP CONVERGENCE

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/11.%20EIGRP/screenshots/eigrpconvergence.jpg" width="90%">

&nbsp;

### Commands

In Router 0 :

```console
Router#show ip route
Gateway of last resort is not set
C 192.168.1.0/24 is directly connected, FastEthernet1/0
C 192.168.2.0/24 is directly connected, FastEthernet0/0
D 192.168.3.0/24 [90/30720] via 192.168.2.2, 00:00:30, FastEthernet0/0
D 192.168.4.0/24 [90/33280] via 192.168.2.2, 00:00:26, FastEthernet0/0
[90/33280] via 192.168.6.1, 00:00:18, FastEthernet0/1
D 192.168.5.0/24 [90/30720] via 192.168.6.1, 00:00:18, FastEthernet0/1
C 192.168.6.0/24 is directly connected, FastEthernet0/1
D 192.168.7.0/24 [90/33280] via 192.168.2.2, 00:00:26, FastEthernet0/0
Router#
```

&nbsp;

Pinging continuously from 192.168.1.2 to 192.168.7.2 

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/11.%20EIGRP/screenshots/eigrp-1.jpg" width="50%">

&nbsp;

In Router 0 :

```console
Router(config)#int fa0/0
Router(config-if)#shut
Router(config-if)#
```

&nbsp;

After shutting down the interface 

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/11.%20EIGRP/screenshots/eigrp-2.jpg" width="50%">

&nbsp;

&nbsp;

## EIGRP AUTO SUMMARY

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/11.%20EIGRP/screenshots/eigrp%20auto%20summary.png" width="60%">

### Commands

In Router 0 :

```console
Router#conf t
Router(config)#router eigrp 1
Router(config-router)#network 192.168.0.0 0.0.255.255
Router(config-router)#
```

In Router 1 :

```console
Router#conf t
Router(config)#router eigrp 1
Router(config-router)#network 192.168.2.0 0.0.0.255
Router(config-router)#network 10.1.1.0 0.0.0.255
Router(config-router)#no auto-summary
```

&nbsp;

## EIGRP LOAD BALANCING

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/11.%20EIGRP/screenshots/loadbalance.png" width="60%">

### Commands

In Router 0 :

```console
Router#show ip route
Gateway of last resort is not set
C 192.168.1.0/24 is directly connected, Ethernet1/0
C 192.168.2.0/24 is directly connected, FastEthernet0/0
D 192.168.3.0/24 [90/30720] via 192.168.2.2, 00:00:26, FastEthernet0/0
C 192.168.4.0/24 is directly connected, FastEthernet0/1
Router#
```

&nbsp;
