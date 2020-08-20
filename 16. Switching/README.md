# SWITCHING AND VLAN

## VLAN 1

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/16.%20Switching/screenshots/vlan1.png" width="90%">

### Commands

In Switch 0 :

```console
Switch#conf t
Switch(config)#vlan 10
Switch(config-vlan)#name VLAN10
Switch(config)#vlan 20
Switch(config-vlan)#name VLAN20
Switch(config)#vlan 30
Switch(config-vlan)#name VLAN30
Switch(config-vlan)#exit
Switch(config)#int fa0/1
Switch(config-if)#switchport access vlan 10
Switch(config-if)#int fa0/2
Switch(config-if)#switchport access vlan 10
Switch(config-if)#int fa0/3
Switch(config-if)#switchport access vlan 20
Switch(config-if)#int fa0/4
Switch(config-if)#switchport access vlan 20
Switch(config-if)#int fa0/5
Switch(config-if)#switchport access vlan 30
Switch(config-if)#int fa0/6
Switch(config-if)#switchport access vlan 30
Switch(config-if)#
```

&nbsp;

## VLAN 2

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/16.%20Switching/screenshots/vlan2.png" width="90%">

### Commands

In Switch 0 :

```console
Switch#conf t
Switch(config)#interface fa0/7
Switch(config-if)#switchport mode trunk
Switch(config-if)#
```

&nbsp;

In Switch 1 :

```console
Switch#conf t
Switch(config)#interface fa0/4
Switch(config-if)#switchport mode trunk
Switch(config-if)#
```

&nbsp;

## Inter-vlan routing

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/16.%20Switching/screenshots/vlansvi.jpg" width="90%">

### Commands

In Switch 0 :

```console
Switch(config)#ip routing
Switch(config)#int vlan 10
Switch(config-if)#
%LINK-5-CHANGED: Interface Vlan10, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan10, changed state to up
Switch(config-if)#
Switch(config-if)#ip add 192.168.1.1 255.255.255.0
Switch(config-if)#int vlan 20
Switch(config-if)#
%LINK-5-CHANGED: Interface Vlan20, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan20, changed state to up
Switch(config-if)#ip add 192.168.2.1 255.255.255.0
Switch(config-if)#
```

&nbsp;
