Day 6 Lab Notes – Routers, MAC Learning, ARP, ICMP, and Packet Structure
Overview

Day 6 focused on how routers connect LANs, how switches learn MAC addresses, how ARP works, and how packets are structured under the hood. I also practiced viewing and clearing ARP tables and MAC address tables on both Windows machines and Cisco switches.
Key Topics Covered

Routers Connect LANs

Routers operate at Layer 3 and are responsible for connecting separate LANs together. They forward packets based on IP addresses and maintain routing tables to determine the best path.
MAC Addresses

    MAC stands for Media Access Control.

    MAC addresses are 48-bit identifiers written in hexadecimal.

    The first 3 bytes (24 bits) are the OUI (Organizationally Unique Identifier), assigned to the manufacturer.

    The last bytes are unique to the specific device.

Hexadecimal Learning

Hex is used heavily in networking for MAC addresses, packet headers, and low-level data representation. I practiced reading and interpreting hex values.
How Switches Learn MAC Addresses

Switches dynamically learn MAC addresses by observing the source MAC of incoming frames.

    Unknown unicast traffic triggers flooding out all ports except the incoming one.

    ARP requests are broadcast to learn the IP-to-MAC mapping.

    Once learned, switches forward frames as unicasts.

Packet Structure

I reviewed the internal structure of packets:

    Ethernet header (destination MAC, source MAC, EtherType)

    IP header (source IP, destination IP, TTL, protocol)

    Transport header (TCP/UDP ports)

    Payload (data)

ARP Behavior

    ARP resolves IP addresses to MAC addresses.

    ARP requests are broadcasts.

    ARP replies are unicasts.

    I viewed ARP entries on Windows using arp -a.

    I viewed ARP entries on Cisco switches using show arp.

MAC Address Table Management

    Viewed MAC address tables using show mac address-table.

    Cleared MAC entries using clear mac address-table dynamic.

    Learned about aging timers: Cisco switches remove inactive MAC entries after 5 minutes.

ICMP Basics

I reviewed the structure of ICMP packets used for pings:

    ICMP Echo Request

    ICMP Echo Reply

    Fields include Type, Code, Checksum, Identifier, and Sequence Number.

Learning Outcomes

    Understood how routers connect LANs and forward packets.

    Learned how switches dynamically build MAC tables.

    Practiced ARP inspection on both Windows and Cisco devices.

    Gained familiarity with packet structure and hex representation.

    Learned how to clear MAC tables and ARP caches.

    Understood ICMP packet flow and structure.

Next Steps

    Practice packet captures with Wireshark.

    Explore VLAN routing (Inter-VLAN routing).

    Document ARP and MAC behavior in more complex topologies.

Summary: Day 6 reinforced core networking fundamentals: MAC learning, ARP behavior, packet structure, and router roles. I practiced real commands and observed how devices communicate at Layer 2 and Layer 3.
