# CONVERGENCE AND CONVERGENCE TIME

## RIP CONVERGENCE TIME

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/10.%20Convergence/screenshots/common-topology.png" width="90%">

### Commands

In Router 0 :

```console
Router#show ip route
Gateway of last resort is not set
C 192.168.1.0/24 is directly connected, FastEthernet1/0
C 192.168.2.0/24 is directly connected, FastEthernet0/0
R 192.168.3.0/24 [120/1] via 192.168.2.2, 00:00:12, FastEthernet0/0
R 192.168.4.0/24 [120/2] via 192.168.2.2, 00:00:12, FastEthernet0/0
[120/2] via 192.168.6.1, 00:00:11, FastEthernet0/1
R 192.168.5.0/24 [120/1] via 192.168.6.1, 00:00:11, FastEthernet0/1
C 192.168.6.0/24 is directly connected, FastEthernet0/1
R 192.168.7.0/24 [120/2] via 192.168.2.2, 00:00:12,
Router#
```

Pinging continuously from 192.168.1.2 to 192.168.7.2 

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/10.%20Convergence/screenshots/rip1.png" width="50%">

In Router 0 :

```console
Router>en
Router#conf t
Router(config)#int fa0/0
Router(config-if)#shut
Router(config-if)#exit
Router(config)exit
Router#
```

After shutting down the interface the ping requests will time out initially and find the alternative path. 

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/10.%20Convergence/screenshots/rip2.png" width="50%">

&nbsp;


## OSPF CONVERGENCE TIME

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/10.%20Convergence/screenshots/common-topology.png" width="90%">

### Commands

In Router 0 :

```console
Router#show ip route
Gateway of last resort is not set
C 192.168.1.0/24 is directly connected, FastEthernet1/0
C 192.168.2.0/24 is directly connected, FastEthernet0/0
O 192.168.3.0/24 [110/2] via 192.168.2.2, 00:00:25, FastEthernet0/0
O 192.168.4.0/24 [110/3] via 192.168.2.2, 00:00:25, FastEthernet0/0
[110/3] via 192.168.6.1, 00:00:25, FastEthernet0/1
O 192.168.5.0/24 [110/2] via 192.168.6.1, 00:00:25, FastEthernet0/1
C 192.168.6.0/24 is directly connected, FastEthernet0/1
O 192.168.7.0/24 [110/3] via 192.168.2.2, 00:00:25, FastEthernet0/0
Router#
```

Pinging continuously from 192.168.1.2 to 192.168.7.2 

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/10.%20Convergence/screenshots/ospf1.png" width="50%">

In Router 0 :

```console
Router>en
Router#conf t
Router(config)#int fa0/0
Router(config-if)#shut
Router(config-if)#
```

After shutting down the interface 

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/10.%20Convergence/screenshots/ospf2.png" width="50%">

&nbsp;
