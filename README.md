# Network-Access-Control-List-ACL-Implementation-Lab

## Overview
This project demonstrates how to implement Extended Access Control Lists (ACLs) to control communication between hosts in a simulated enterprise network using Cisco Packet Tracer.  

## Objective
- Block Guest PC from pinging Admin PC
- Allow all other network communication
- Simulate real-world firewall behavior using router-based ACLs

## Network Topology
Topology Type:
The Tree / Hierarchical Star was used to stimulate a segmented corporate environment
- Core Layer: 1x 2911 Router
- 2x 2960 Switches
  - Switch 1:
        - Admin PC: 192.168.10.10 (The Protected Host)
        - HR PC: 192.168.10.20
  - Switch 2:
        - IT PC: 192.168.20.10
        - Guest PC: 192.168.20.20 (The Restricted Host)
## ACL Configuration
Router>enable
Router#configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#access-list 100 deny icmp host 192.168.20.20 host 192.168.10.10 echo
Router(config)#access-list 100 permit ip any any
Router(config)#interface gigabitEthernet 0/1
Router(config-if)#ip access-group 100 in
Router(config-if)#end
Router#

STEP 1 — ENTER CONFIG MODE  
On the router CLI:  
enable  
configure terminal    

STEP 2 — CREATE THE BLOCK RULE  
access-list 100 deny icmp host 192.168.20.20 host 192.168.10.10 echo

STEP 3 — ALLOW ALL OTHER TRAFFIC
access-list 100 permit ip any any

STEP 4 — APPLY THE ACL TO THE INTERFACE
interface gigabitEthernet0/1
ip access-group 100 in

end
