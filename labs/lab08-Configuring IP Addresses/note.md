Day 8 Lab Notes – IPv4 Addressing, Network Ranges, and Cisco IP Configuration
Overview

Day 8 focused on strengthening IPv4 addressing fundamentals, calculating usable host ranges, and configuring IP addresses directly on Cisco devices. This day builds the foundation for subnetting, routing, and all future CCNA labs.
IPv4 Address Classes

IPv4 addresses are divided into classes based on the first octet:

    Class A: 1–126

    Class B: 128–191

    Class C: 192–223

    Class D: 224–239 (multicast)

    Class E: 240–255 (experimental)

Classes A, B, and C are used for standard unicast networking.
Key Address Components

Every IPv4 network contains:

    Network Address – identifies the network (all host bits = 0)

    Broadcast Address – used to reach all hosts (all host bits = 1)

    First Usable Host – network address + 1

    Last Usable Host – broadcast address − 1

    Maximum Number of Hosts – (2^n - 2), where (n) is the number of host bits

Example Calculation

For a network like 192.168.10.0/24:

    Network: 192.168.10.0

    Broadcast: 192.168.10.255

    First usable: 192.168.10.1

    Last usable: 192.168.10.254

    Hosts: 254

These calculations apply to any subnet once I determine the number of host bits.
Configuring IP Addresses on Cisco Devices

I practiced assigning IPv4 addresses to interfaces using Cisco IOS.
Interface Configuration Steps

    Enter global configuration mode:

    configure terminal

    Select an interface:

    interface g0/0

    Assign an IP address and subnet mask:

    ip address 192.168.10.1 255.255.255.0

    Enable the interface:

    no shutdown

Verification Commands

    Check interface status:

    show ip interface brief

    View full interface details:

    show running-config

Learning Outcomes

    Identified IPv4 address classes and their ranges.

    Calculated network, broadcast, first/last usable addresses, and host counts.

    Strengthened understanding of how subnet masks define host bits.

    Configured IPv4 addresses on Cisco router and switch interfaces.

    Verified interface configuration using show commands.

Next Steps

    Begin subnetting practice with /25, /26, /27, and /30 networks.

    Configure multiple interfaces and test connectivity with pings.

    Document subnetting examples for future CCNA labs.
    
