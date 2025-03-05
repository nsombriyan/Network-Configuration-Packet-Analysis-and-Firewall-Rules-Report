# Network-Configuration-Packet-Analysis-and-Firewall-Rules-Report
***How to set up a small network, analyze network traffic (using wireshark), and configure firewall rules using cisco packet tracer.***

## Network Configuration (With Cisco packet tracer)
*To set up the networ, the network should have;*
1. A Router (I used Cisco2811),
2. A Switch (I used Cisco2960),
3. Computers (I used 4 descktops)
4. and also a DHCP Server Configured on the router

### Configure VLANs on the switch
1. Open the switch CLI and Enter the following commands
   >- enable 
   >- config t
   >- vlan 10
   >- name VLAN10
   >- exit
   >- config t
   >- vlan 20
   >- name VLAN20
   >- exit
   >- interface fa0/1
   >- switchport mode access
   >- switchport access vlan 10
   >- exit
   >- interface fa0/2
   >- switchport mode access
   >- switchport access vlan 10
   >- exit
   >- interface fa0/3
   >- switchport mode access
   >- switchport access vlan 20
   >- exit
   >- interface fa0/4
   >- switchport mode access
   >- switchport access vlan 20
  2. Set Up a Trunk Port for the router
   >- interface fa0/5
   >- switchport mode trunk
   >- exit
### Configure Router for inte-VLAN Routing
>- enable
>- config t
>- interface fa0/0
>- no shutdown
>- exit
>- interface fa0/0.10
>- encapsulate dot1q 10
>- ip address 192.168.10.1 255.255.255.0
>- exit
>- interface fa0/0.20
>- encapsulate dot1q 20
>- ip address 192.168.20.1 255.255.255.0
>- exit

### Configure DHCP on the Router

### Configure Static and Dyamic Routing
*Static Routing*
*Dynamic Routing*

## Packet Analysis with (*Wireshark*)
###To analyze network trafic;
1. Open wireshark
2. Select the active network interfaces
3. Click on start capturing and let it run

*Analyzing Network Protocol HTTP Traffic*
1. Use filter: HTTP
2. Looking for GET and POST requests

*Analyzing ARP (Address Resolution Protocol)*
1. Use filter: HTTP
2. Checking for ARP poisoning

*Analyzing DNS (Domain Name System) Traffic*
1. Use filter: DNS
2. Check if DNS responses are from trusted server.

### Identifying Abnormal Traffic


## Fierwall Rules & Access Control List (ACLs)
