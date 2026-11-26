
Coffee Shop Network

Overview

A segmented small-business network designed and simulated in Cisco Packet Tracer for a coffee shop environment. The topology isolates internal management, point-of-sale (POS) operations, and public guest Wi-Fi traffic across dedicated VLANs with inter-VLAN routing, traffic filtering, and hardened device management.

Network Topology

Devices & Infrastructure

• Router: Cisco 2911 (Coffeeshop-RTR) connected to an ISP cloud (Cloud-PT)
• Switch: Cisco Catalyst 3560-24PS Multilayer Switch (COffeeShop-SW)
• Wireless: Wireless Access Point (AccessPoint-PT) for guest Wi-Fi
• End Devices: Manager PC, Office Printer, POS Terminal, Receipt Printer, and Guest Laptops

VLAN & Subnet Design

VLAN ID	Name	Subnet / Gateway	Connected Devices

VLAN 10 (Green)
	Management_Office	192.168.10.0/24 (192.168.10.1)	Manager PC, Office Printer
	
VLAN 20 (Orange)
	POS	192.168.20.0/24 (192.168.20.1)	POS Terminal, Receipt Printer
	
VLAN 30 (Yellow)
	Guest_WIFI	192.168.30.0/24 (192.168.30.1)	Guest Wireless AP, Guest Laptops
	
VLAN 99 
	Network_Management	192.168.99.0/24 (192.168.99.2)	Switch SVI Management Interface


Key Configurations & Security Features

• VLAN Segmentation & Trunking: Configured 802.1Q trunking (GigabitEthernet0/1) between the multilayer switch and router, restricting allowed traffic to VLANs 10, 20, 30, and 99, with spanning-tree portfast enabled on access ports.

• Guest Isolation / Traffic Filtering: Restricted Guest Wi-Fi (192.168.30.0/24) from reaching internal Management (192.168.10.0/24) and POS (192.168.20.0/24) subnets while preserving gateway reachability (192.168.30.1).

• Device Hardening & Remote Access: Configured encrypted privileged EXEC passwords (enable secret), Hostname, password encryption service, MOTD warning banners, disabled DNS lookups, and enabled SSHv2 with 1200-bit RSA keys and local authentication on VTY lines, Exec-Timeout.
