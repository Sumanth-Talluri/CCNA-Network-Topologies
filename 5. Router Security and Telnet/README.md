# Router Security and Telnet

## Router Security

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/5.%20Router%20Security%20and%20Telnet/screenshots/routersec.PNG" width="90%">

### Commands

In Router 0 :

```console
Router(config)#enable secret cisco123
Router(config)#
Router(config)#do show running-config
Building configuration...
Current configuration : 535 bytes
!
version 12.4
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname Router
!
!
enable secret 5 $1$mERr$5.a6P4JqbNiMX01usIfka/
!
Router#
```

&nbsp;

## TELNET

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/5.%20Router%20Security%20and%20Telnet/screenshots/telnet.png" width="70%">

### Commands

In Router 0 :

```console
Router>en
Router#conf t
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#enable secret cisco123
Router(config)#line vty 0 4
Router(config-line)#password cisco
Router(config-line)#exit
Router(config)#
```

&nbsp;

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/5.%20Router%20Security%20and%20Telnet/screenshots/telnetcmd.png" width="50%">

