# Overview
Currently, every service is located on 192.168.0.X
Eventually, once VLANS are created, each VLAN will be using the /24 subnetting prefix. 

# Final Structure:
- VLAN 10   Management   10.10.10.0/24
- VLAN 20   Servers   10.10.20.0/24 
- VLAN 30   Storage   10.10.30.0/24
- VLAN 40   Kubernetes   10.10.40.0/24
- VLAN 50   IoT   10.10.50.0/24
- VLAN 60   Guest   10.10.60.0/24
- VLAN 70   Experimental   10.10.70.0/24
