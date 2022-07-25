## Part 1. **ipcalc** tool

#### 1.1 Networks and Masks

##### 1). Network address of 192.167.38.54/13
<div align="center">

![1.1.1](./Attachments/1.1.1.png)
<br>
<i>ipcalc output</i>

</div>

##### 2) Conversion of the mask 255.255.255.0 to prefix and binary, /15 to normal and binary, 11111111.11111111.11111111.11110000 to normal and prefix

<div align="center">

![1.1.2](./Attachments/1.1.2.png)
<br>
<i>mask 255.255.255.0 conversion</i>

![1.1.2.2](./Attachments/1.1.2.2.png)
<br>
<i>mask /15 conversion</i>

![1.1.2.3](./Attachments/1.1.2.3.png)
<br>
<i>mask 11111111.11111111.11111111.11110000  conversion</i>

</div>

##### 3) Minimum and maximum host in 12.167.38.4 network with masks: /8, 11111111.11111111.00000000.00000000, 255.255.254.0 and /4

<div align="center">

![1.1.3.1](./Attachments/1.1.3.1.png)
<br>
<i>Minimum and maximum host in 12.167.38.4 network with mask: /8</i>

![1.1.3.2](./Attachments/1.1.3.2.png)
<br>
<i>Minimum and maximum host in 12.167.38.4 network with mask: /11111111.11111111.00000000.00000000</i>

![1.1.3.3](./Attachments/1.1.3.3.png)
<br>
<i>Minimum and maximum host in 255.255.254.0 network with mask: /4</i>

</div>

#### 1.2. localhost

- can be accessed with 
	- 127.0.0.2
	- 127.1.0.1
- can’t with 
	- 194.34.23.100
	- 128.0.0.1

#### 1.3. Network ranges and segments

##### 1) which of the listed IPs can be used as public and which only as private: 10.0.0.45, 134.43.0.2, 192.168.4.2, 172.20.250.4, 172.0.2.1, 192.172.0.1, 172.68.0.2, 172.16.255.255, 10.10.10.10, 192.169.168.1

- private
	- 10.0.0.45
	- 192.168.4.2
	- 172.20.250.4
	- 172.16.255.255
	- 10.10.10.10
- public
	- 134.43.0.2
	- 172.0.2.1
	- 192.172.0.1
	- 172.68.0.2
	- 192.169.168.1

##### 2) which of the listed gateway IP addresses are possible for 10.10.0.0/18 network: 10.0.0.1, 10.10.0.2, 10.10.10.10, 10.10.100.1, 10.10.1.255

- possible
	- 10.10.0.2
	- 10.10.10.10
	- 10.10.1.255
- impossible
	- 10.0.0.1
	- 10.10.100.1

## Part 2. Static routing between two machines


<div align="center">

![2.0.1](./Attachments/2.0.1.png)
<br>
<i>ws1 interfaces</i>

![2.0.2](./Attachments/2.0.2.png)
<br>
<i>ws2 interfaces</i>

![2.0.3](./Attachments/2.0.3.png)
<br>
<i>ws1 etc/netplan/00-installer-config.yaml</i>

![2.0.4](./Attachments/2.0.4.png)
<br>
<i>ws2 etc/netplan/00-installer-config.yaml</i>

</div>


#### 2.1. Adding a static route manually

<div align="center">

![2.1.1](./Attachments/2.1.1.png)
<br>
<i>ip r and ping to ws2</i>

![2.1.2](./Attachments/2.1.2.png)
<br>
<i>ip r and ping to ws1</i>

</div>


#### 2.2. Adding a static route with saving

<div align="center">

![2.2.1](./Attachments/2.2.1.png)
<br>
<i>ws1 etc/netplan/00-installer-config.yaml</i>

![2.2.2](./Attachments/2.2.2.png)
<br>
<i>ws2 etc/netplan/00-installer-config.yaml</i>

![2.2.3](./Attachments/2.2.3.png)
<br>
<i>ping to ws2</i>

![2.2.4](./Attachments/2.2.4.png)
<br>
<i>ping to ws2</i>

</div>

## Part 3. **iperf3** utility

#### 3.1. Connection speed

`8Mbps` &rarr; `1MB/s`

`100MB/s` &rarr; `819200Kbps`

`1Gbps` &rarr; `1024Mbps`

#### 3.2. **iperf3** utility

<div align="center">

![3.2.1](./Attachments/3.2.1.png)
<br>
<i>iperf3 server side</i>

![3.2.2](./Attachments/3.2.2.png)
<br>
<i>iperf3 client side</i>

</div>


## Part 4. Network firewall

#### 4.1. **iptables** utility

<div align="center">

![4.1.1](./Attachments/4.1.1.png)
<br>
<i>ws1 /etc/firewall file</i>

![4.1.2](./Attachments/4.1.2.png)
<br>
<i>ws2 /etc/firewall file</i>

![4.1.3](./Attachments/4.1.3.png)
<br>
<i>ws1 ping ws2</i>

![4.1.4](./Attachments/4.1.4.png)
<br>
<i>ws2 ping ws1</i>

</div>

In the first strategy, we allow everything that is not prohibited, and in the second we prohibit everything that is not allowed. But when writing rules, it is worth considering that the forbidding rules do not overwritten with the permissive ones

#### 4.2. **nmap** utility

<div align="center">

![4.2.1](./Attachments/4.2.1.png)
<br>
<i>nmap command output</i>

</div>

## Part 5. Static network routing

#### 5.1. Configuration of machine addresses


<div align="center">

![5.1.1](./Attachments/5.1.1.png)
<br>
<i>ws11 etc/netplan/00-installer-config.yaml</i>

![5.1.2](./Attachments/5.1.2.png)
<br>
<i>ws21 etc/netplan/00-installer-config.yaml</i>

![5.1.3](./Attachments/5.1.3.png)
<br>
<i>ws22 etc/netplan/00-installer-config.yaml</i>

![5.1.4](./Attachments/5.1.4.png)
<br>
<i>r1 etc/netplan/00-installer-config.yaml</i>

![5.1.5](./Attachments/5.1.5.png)
<br>
<i>r2 etc/netplan/00-installer-config.yaml</i>

![5.1.6](./Attachments/5.1.6.png)
<br>
<i>ws11 ip -4 a output and ping r1</i>

![5.1.7](./Attachments/5.1.7.png)
<br>
<i>ws21 ip -4 a output and ping ws22</i>

![5.1.8](./Attachments/5.1.8.png)
<br>
<i>ws22 ip -4 a output</i>

![5.1.9](./Attachments/5.1.9.png)
<br>
<i>r1 ip -4 a output</i>

![5.1.10](./Attachments/5.1.10.png)
<br>
<i>r2 ip -4 a output</i>

</div>


#### 5.2. Enabling IP forwarding.

<div align="center">

![5.2.1](./Attachments/5.2.1.png)
<br>
<i>sysctl -w net.ipv4.ip_forward=1 command output for r1</i>

![5.2.2](./Attachments/5.2.2.png)
<br>
<i>sysctl -w net.ipv4.ip_forward=1 command output for r2</i>

![5.2.3](./Attachments/5.2.3.png)
<br>
<i>r1 /etc/sysctl.conf file</i>

![5.2.4](./Attachments/5.2.4.png)
<br>
<i>r2 /etc/sysctl.conf file</i>

</div>

#### 5.3. Default route configuration

<div align="center">

![5.3.1](./Attachments/5.3.1.png)
<br>
<i>gateway for ws11</i>

![5.3.2](./Attachments/5.3.2.png)
<br>
<i>gateway for ws21</i>

![5.3.3](./Attachments/5.3.3.png)
<br>
<i>gateway for ws22</i>

![5.3.4](./Attachments/5.3.4.png)
<br>
<i>ws11 ping r2</i>

![5.3.5](./Attachments/5.3.5.png)
<br>
<i>r2 tcpdump command output</i>

![5.3.6](./Attachments/5.3.6.png)
<br>
<i>ws11 ip r command output</i>


![5.3.7](./Attachments/5.3.7.png)
<br>
<i>ws21 ip r command output</i>


![5.3.8](./Attachments/5.3.8.png)
<br>
<i>ws22 ip r command output</i>

</div>

#### 5.4. Adding static routes

<div align="center">

![5.4.1](./Attachments/5.4.1.png)
<br>
<i>r1 etc/netplan/00-installer-config.yaml</i>


![5.4.2](./Attachments/5.4.2.png)
<br>
<i>r2 etc/netplan/00-installer-config.yaml</i>

![5.4.3](./Attachments/5.4.3.png)
<br>
<i>ip r command output for r1</i>


![5.4.4](./Attachments/5.4.4.png)
<br>
<i>ip r command output for r2</i>


![5.4.5](./Attachments/5.4.5.png)
<br>
<i>ip r list 10.10.0.0/18 and ip r list 0.0.0.0/0 commands output</i>

</div>

since the router always chooses a path with a larger mask, the default path will never be selected if there is another path

#### 5.5. Making a router list

<div align="center">

![5.5.1](./Attachments/5.5.1.png)
<br>
<i>traceroute 10.20.0.10 command output</i>

![5.5.2](./Attachments/5.5.2.png)
<br>
<i>tcpdump -tnv -i enp0s8 command output</i>

</div>

traceroute sends packets, increasing the TTL until it reaches the target

#### 5.6. Using **ICMP** protocol in routing

<div align="center">

![5.6.1](./Attachments/5.6.1.png)
<br>
<i>ping -c 1 10.30.0.111 command output</i>

![5.6.2](./Attachments/5.6.2.png)
<br>
<i>traceroute -n -i enp0s8 command output</i>

</div>

## Part 6. Dynamic IP configuration using **DHCP**

##### 1) specify the default router address, DNS-server and internal network address. Here is an example of a file for r2:


<div align="center">

![6.1](./Attachments/6.1.png)
<br>
<i>/etc/dhcp/dhcpd.conf file</i>

</div>

##### 2) Write `nameserver 8.8.8.8`. in a resolv.conf file

<div align="center">

![6.2](./Attachments/6.2.png)
<br>
<i>r2 /etc/resolv.config file</i>

![6.3](./Attachments/6.3.png)
<br>
<i>ip a command output and ping to ws22</i>

![6.4](./Attachments/6.4.png)
<br>
<i>systemctl restart isc-dhcp-server command output</i>

![6.5](./Attachments/6.5.png)
<br>
<i>ws11 /etc/netplan/00-installer-config.yaml file</i>

![6.6](./Attachments/6.6.png)
<br>
<i>r1 /etc/resolv.config file</i>

![6.10](./Attachments/6.10.png)
<br>
<i>ws11 ip a command output</i>

![6.8](./Attachments/6.8.png)
<br>
<i>ping ws21 form w11</i>

![6.9](./Attachments/6.9.png)
<br>
<i>ws21 dhclient update</i>

</div>

- used dhcp options:
	- domain-name-servers - DNS server IP addresses
	- routers - default gateway IP addresses

## Part 7. **NAT**

##### 1) Delete rules in the filter table - `iptables -F`

##### 2) Delete rules in the "NAT" table - `iptables -F -t nat`

##### 3) Drop all routed packets - `iptables --policy FORWARD DROP`

##### 4) Allow routing of all **ICMP** protocol packets

<div align="center">

![7.1](./Attachments/7.1.png)
<br>
<i>r1 /etc/apache2/ports.conf file</i>

![7.2](./Attachments/7.2.png)
<br>
<i>ws22 /etc/apache2/ports.conf file</i>

![7.3](./Attachments/7.3.png)
<br>
<i>service apache2 start command on r1</i>

![7.4](./Attachments/7.4.png)
<br>
<i>service apache2 start command on ws22</i>

![7.5](./Attachments/7.5.png)
<br>
<i>r2 firewall settings</i>

![7.6](./Attachments/7.6.png)
<br>
<i>r2 firewall start</i>

![7.7](./Attachments/7.7.png)
<br>
<i>ping ws22 form r1</i>

![7.8](./Attachments/7.8.png)
<br>
<i>ping ws22 from r1 with new rules to allow icmp</i>

</div>

##### 5) Enable **SNAT**, which is masquerade all local ip from the local network behind r2 (as defined in Part 5 - network 10.20.0.0)

##### 6) Enable **DNAT** on port 8080 of r2 machine and add external network access to the Apache web server running on ws22

<div align="center">

![7.9](./Attachments/7.9.png)
<br>
<i>r2 firewall file</i>

![7.10](./Attachments/7.10.png)
<br>
<i>telnet from r1 to ws22</i>

![7.11](./Attachments/7.11.png)
<br>
<i>telnet from ws22 to r1</i>

</div>

## Part 8. Bonus. Introduction to **SSH Tunnels**

<div align="center">

![8.7](./Attachments/8.7.png)
<br>
<i>/etc/apahe2/ports.conf file</i>


![8.0](./Attachments/8.0.png)
<br>
<i>apache2 server start</i>


![8.1](./Attachments/8.5.png)
<br>
<i>local ssh</i>

![8.2](./Attachments/8.4.png)
<br>
<i>telnet 127.0.0.1 3333 command output</i>


![8.3](./Attachments/8.2.png)
<br>
<i>remote ssh</i>


![8.4](./Attachments/8.3.png)
<br>
<i>telnet 127.0.0.1 3000 command output</i>

</div>

