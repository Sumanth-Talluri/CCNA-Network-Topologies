# FIRST HOP REDUNDANCY PROTOCOL (FHRP)

## HSRP

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/14.%20FHRP/screenshots/HSRP.png" width="60%">

### Commands

In Router 1 :

```console
Router>en
Router#conf t
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#int fa0/0
Router(config-if)#standby 1 ip 192.168.1.1
Router(config-if)#
```

In Router 2 :

```console
Router>en
Router#conf t
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#int fa0/0
Router(config-if)#standby 1 ip 192.168.1.1
Router(config-if)#
```

&nbsp;
