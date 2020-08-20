# Best Path Calculation

## Path Calculation RIP

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/09.%20Best%20Path%20Calculation/screenshots/rip%20calculation.png" width="90%">

&nbsp;

## Path Calculation OSPF

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/09.%20Best%20Path%20Calculation/screenshots/ospf%20calculation.png" width="90%">

### Commands

In Router 0 :

```console
Router#show ip route
Gateway of last resort is not set
C 192.168.1.0/24 is directly connected, FastEthernet0/1
C 192.168.2.0/24 is directly connected, Ethernet1/0
O 192.168.3.0/24 [110/14] via 192.168.4.2, 00:14:34, FastEthernet0/0
C 192.168.4.0/24 is directly connected, FastEthernet0/0
O 192.168.5.0/24 [110/2] via 192.168.4.2, 00:14:54, FastEthernet0/0
O 192.168.6.0/24 [110/3] via 192.168.4.2, 00:14:34, FastEthernet0/0
O 192.168.7.0/24 [110/4] via 192.168.4.2, 00:14:34, FastEthernet0/0
O 192.168.8.0/24 [110/5] via 192.168.4.2, 00:14:34, FastEthernet0/0
Router#
```
