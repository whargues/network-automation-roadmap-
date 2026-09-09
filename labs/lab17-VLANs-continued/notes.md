Overview

Today expanded on VLANs by introducing trunking, tagged vs untagged ports, 802.1Q, native VLAN behavior, and ROAS (Router‑on‑a‑Stick). These concepts explain how VLANs scale beyond small networks and how multiple VLANs can travel over a single physical link.
Key Concepts Learned
Why Trunks Are Needed

In small networks, you could connect switches together using separate interfaces for each VLAN.
But in real networks, this is not scalable.

Example problem:

    VLAN 10 needs a link

    VLAN 20 needs a link

    VLAN 30 needs a link
    You’d waste ports and cables.

Solution: A trunk.

A trunk allows multiple VLANs to travel over one physical interface.
Tagged vs Untagged Ports

I learned the naming conventions:

    Access port → untagged → carries one VLAN

    Trunk port → tagged → carries multiple VLANs

Switches tag frames with VLAN IDs when sending them over a trunk.
Trunking Protocols

Two main trunking protocols exist:
ISL (Inter‑Switch Link)

    Old Cisco‑proprietary protocol

    No longer used

    Not supported on modern switches

IEEE 802.1Q

    Industry standard

    Used everywhere

    Inserts a VLAN tag into the Ethernet header

    Supports VLANs 1–4094

I saw how the 802.1Q tag sits inside the Ethernet frame.
VLAN Ranges

802.1Q divides VLANs into two groups:

    1–1005 → normal range

    1006–4094 → extended range

Cisco switches always have:

    VLAN 1 (default)

    VLANs 1002–1005 (legacy FDDI/Token Ring)

Native VLAN

The native VLAN is the VLAN that travels untagged across a trunk.

Important behaviors:

    Default native VLAN = 1

    Switch does not tag frames belonging to the native VLAN

    When a switch receives an untagged frame on a trunk, it assumes it belongs to the native VLAN

    Native VLANs must match on both sides of a trunk

        If they don’t match → VLAN leaks, security issues, weird traffic behavior

Security Best Practice

Change the native VLAN to something other than 1.
Router‑on‑a‑Stick (ROAS)

ROAS allows a router to route between multiple VLANs using one physical link.

How it works:

    Switch port → trunk

    Router interface → divided into subinterfaces

    Each subinterface is assigned:

        An IP address

        A VLAN tag using encapsulation dot1Q <vlan-id>

Example:

interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

This allows the router to perform inter‑VLAN routing.
Commands Practiced
Configure a trunk

interface g0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30
switchport trunk native vlan 99

Add/remove VLANs from a trunk

switchport trunk allowed vlan add 30
switchport trunk allowed vlan remove 20

Create router subinterfaces (ROAS)

interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

Learning Outcomes

    Understood why trunks are required in scalable networks

    Learned the difference between tagged (trunk) and untagged (access) ports

    Reviewed ISL vs 802.1Q

    Learned VLAN ranges and legacy VLANs

    Understood native VLAN behavior and security concerns

    Practiced trunk configuration and VLAN tagging

    Built router subinterfaces for ROAS

    Saw how inter‑VLAN routing works over a single link

Key Takeaways

    Trunks carry multiple VLANs over one interface

    Access ports carry one VLAN

    802.1Q is the modern tagging standard

    Native VLAN must match on both ends

    ROAS allows routing between VLANs using subinterfaces

    VLAN tagging is essential for multi‑VLAN networks
    
