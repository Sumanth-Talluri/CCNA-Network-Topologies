# DNS and DHCP

## DOMAIN NAME SYSTEM (DNS)

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/4.%20DNS%20and%20DHCP/screenshots/DNS%20Server.PNG" width="90%">

&nbsp;

## DYNAMIC HOST CONFIGURATION PROTOCOL (DHCP)

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/4.%20DNS%20and%20DHCP/screenshots/dhcp.jpg" width="90%">

### Commands

In Router 0 :

```console
Router(config)#ip dhcp pool one
Router(dhcp-config)#network 192.168.1.0 255.255.255.0
Router(dhcp-config)#default-router 192.168.1.1
Router(dhcp-config)#dns-server 8.8.8.8
Router(config)#ip dhcp pool two
Router(dhcp-config)#network 192.168.2.0 255.255.255.0
Router(dhcp-config)#default-router 192.168.2.1
Router(dhcp-config)#dns-server 8.8.8.8
```
