# ACCESS CONTROL LIST (ACL)

## STANDARD ACL

### Task 1

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/s-task1.png" width="90%">

### Commands

In Router 0 :

```console
Router#conf t
Router(config)#access-list 1 deny host 192.168.1.2
Router(config)#access-list 1 permit any
Router(config)#int fa0/1
Router(config-if)#ip access-group 1 out
Router(config-if)#exit
Router(config)#do show access-list
Standard IP access list 1
deny host 192.168.1.2
permit any
Router(config)#
```

&nbsp;

### Task 2

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/s-task2.png" width="90%">

### Commands

In Router 1 :

```console
Router#conf t
Router(config)#access-list 1 deny host 192.168.1.2
Router(config)#access-list 1 permit any
Router(config)#int fa0/0
Router(config-if)#ip access-group 1 out
Router(config-if)#
```

&nbsp;

### Task 3

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/s-task3.png" width="90%">

### Commands

In Router 1 :

```console
Router(config)#access-list 1 deny host 192.168.1.2
Router(config)#access-list 1 permit any
Router(config)#int fa0/0
Router(config-if)#ip access-group 1 out
Router(config-if)#int fa0/1
Router(config-if)#ip access-group 1 out
Router(config-if)#
```

&nbsp;

### Task 4

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/s-task4.png" width="90%">

### Commands

In Router 1 :

```console
Router(config)#access-list 1 permit host 192.168.2.3
Router(config)#access-list 1 deny 192.168.2.0 0.0.0.255
Router(config)#access-list 1 permit any
Router(config)#int fa0/1
Router(config-if)#ip access-group 1 out
Router(config-if)#
```

&nbsp;

### Task 5

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/s-task5.png" width="90%">

### Commands

In Router 1 :

```console
Router#conf t
Router(config)#access-list 1 deny 192.168.1.0 0.0.0.255
Router(config)#access-list 1 permit any
Router(config)#int fa0/0
Router(config-if)#ip access-group 1 out
Router(config-if)#
```

&nbsp;

## EXTENDED ACL

### Task 1

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/e-task1.png" width="90%">

### Commands

In Router 0 :

```console
Router>en
Router#conf t
Router(config)#access-list 100 deny ip host 192.168.1.2 192.168.2.0 0.0.0.255
Router(config)#access-list 100 permit ip any any
Router(config)#int fa0/0
Router(config-if)#ip access-group 100 in
Router(config-if)#exit
Router(config)#
```

&nbsp;

### Task 2

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/e-task2.png" width="90%">

### Commands

In Router 0 :

```console
Router#conf t
Router(config)#access-list 100 deny ip 192.168.1.0 0.0.0.255 192.168.4.0 0.0.0.255
Router(config)#access-list 100 permit ip any any
Router(config)#int fa0/0
Router(config-if)#ip access-group 100 in
Router(config-if)#
```

&nbsp;

### Task 3

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/e-task3.png" width="90%">

### Commands

In Router 0 :

```console
Router#conf t
Router(config)#access-list 100 deny ip host 192.168.1.2 host 192.168.2.2
Router(config)#access-list 100 permit ip any any
Router(config)#int fa0/0
Router(config-if)#ip access-group 100 in
Router(config-if)#exit
Router(config)#exit
Router#
```

&nbsp;

### Task 4

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/s-task4.png" width="90%">

### Commands

In Router 0 :

```console
Router#conf t
Router(config)#access-list 100 deny ip host 192.168.1.2 host 192.168.5.3
Router(config)#access-list 100 permit ip any any
Router(config)#int fa0/0
Router(config-if)#ip access-group 100 in
Router(config-if)#exit
Router(config)#exit
Router#
```

&nbsp;

### Task 5

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/e-task5.png" width="90%">

### Commands

In Router 0 :

```console
Router#conf t
Router(config)#access-list 100 deny tcp host 192.168.1.2 host 192.168.5.3 eq 80
Router(config)#access-list 100 permit ip any any
Router(config)#int fa0/0
Router(config-if)#ip access-group 100 in
Router(config-if)#exit
Router(config)#exit
```

From 192.168.1.2, accessing the webpage of 192.168.5.3

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/e-task5-output.png" width="50%">

&nbsp;

### Task 6

### Topology

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/e-task6.png" width="90%">

### Commands

In Router 0 :

```console
Router#conf t
Router(config)#access-list 100 deny icmp host 192.168.1.2 host 192.168.5.3
Router(config)#access-list 100 permit ip any any
Router(config)#int fa0/0
Router(config-if)#ip access-group 100 in
Router(config-if)#exit
Router(config)#exit
Router#
```

From 192.168.1.2 accessing the webpage of 192.168.5.3

<img align="center" src="https://github.com/Sumanth-Talluri/CCNA-Network-Topologies/blob/master/12.%20ACL/screenshots/e-task6-output.png" width="50%">
