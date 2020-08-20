# Per VLAN Spanning Tree Protocol (PVSTP)

## Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/17.%20STP/screenshots/pvstp.jpg" width="100%">

## Commands

&nbsp;

In Switch 0 :

```console
Switch>en
Switch#conf t
Switch(config)#spanning-tree vlan 10 priority 4096
Switch(config)#
```
&nbsp;

In Switch 1 :

```console
Switch>en
Switch#conf t
Switch(config)#spanning-tree vlan 20 priority 4096
Switch(config)#
```
&nbsp;

In Switch 2 :

```console
Switch>en
Switch#conf t
Switch(config)#spanning-tree vlan 30 priority 4096
Switch(config)#
```
&nbsp;
