Overview

This lesson introduced VLANs and explained why they are critical for network segmentation. I learned that a LAN is defined as a single broadcast domain, not just a group of PCs in a small area. VLANs allow switches to split one physical network into multiple logical broadcast domains.
Key Concepts Learned
LANs and Broadcast Domains

    A LAN = one broadcast domain.

    Without VLANs, broadcasts flood every device on the switch, even across different IP subnets.

    Layer 3 rules alone do not stop Layer 2 broadcasts.

What VLANs Solve

    VLANs create separate broadcast domains at Layer 2.

    Each VLAN isolates traffic so broadcasts stay within their VLAN.

    This segmentation improves performance, security, and design flexibility.

Default and Legacy VLANs

    VLAN 1 = default VLAN (all ports belong here initially).

    VLANs 1002–1005 = legacy VLANs (Token Ring/FDDI), still present on Cisco switches.

Switch vs Router Roles

    Switches: enforce VLAN separation at Layer 2.

    Routers (or Layer 3 switches): perform Inter‑VLAN routing so devices in different VLANs can communicate.

Cisco Commands Practiced
View VLANs
show vlan brief

Create a VLAN
vlan 10
name Accounting

Assign a Port to a VLAN
interface g0/1
switchport mode access
switchport access vlan 10

Learning Outcomes

    Understood that a LAN = broadcast domain.

    Learned how VLANs isolate broadcasts into separate domains.

    Reviewed default VLAN 1 and legacy VLANs 1002–1005.

    Practiced basic VLAN configuration commands.

    Learned that routers (or L3 switches) handle communication between VLANs.

Key Takeaways

    VLANs are a Layer 2 solution to broadcast flooding.

    They provide segmentation, security, and scalability.

    Switches separate VLANs, routers connect them.

    VLANs are the foundation for trunking, 802.1Q tagging, and router‑on‑a‑stick.
