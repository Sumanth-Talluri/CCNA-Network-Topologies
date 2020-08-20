# Static Routing to ISP

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/03.%20Static%20Routing%20to%20ISP/screenshots/topology.png" width="90%">

&nbsp;

### Commands

Configuring static routing to Facebook Network :

```console
Router(config)#ip route 173.252.0.0 255.255.0.0 192.168.2.2
```

Now let us configure static routing to Google Network :

```console
Router(config)#ip route 74.0.0.0 255.0.0.0 192.168.2.2
```

&nbsp;

From the web browser of 192.168.1.2 ping to Facebook server(http://74.252.110.27) and Google Server(http://74.125.236.87) using its IP address. 
The ping result yields the respective web page.

&nbsp;

<p>
<img src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/03.%20Static%20Routing%20to%20ISP/screenshots/FB.png" width="47%">
<img src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/03.%20Static%20Routing%20to%20ISP/screenshots/google.png" width="47%">
</p>
