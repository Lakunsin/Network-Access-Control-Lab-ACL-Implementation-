# Network-Access-Control-List-ACL-Implementation-Lab

## Overview
This project demonstrates how to implement Extended Access Control Lists (ACLs) to control communication between hosts in a simulated enterprise network using Cisco Packet Tracer.  

## Objective
- Block Guest PC from pinging Admin PC
- Allow all other network communication
- Simulate real-world firewall behavior using router-based ACLs

## Network Topology
Topology Type:
Tree / Hierarchical Star
        Router (Core)
        /        \
   Switch1     Switch2
    /   \       /   \
  PC1  PC2   PC3   PC4
  

Project Goal: Isolate PC4 from PC1 while maintaining overall network connectivity.  
Topology: Hierarchical (Tree) topology using 1 Router and 2 Switches.  
The Challenge: Resolving the "Two-Way ICMP" issue where blocking a source also blocks the return path.  
The Solution: Implementing specific ICMP type filtering - echo  
