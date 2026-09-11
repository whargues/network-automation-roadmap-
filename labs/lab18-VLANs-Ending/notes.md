Overview

This final VLAN lab covered how to configure native VLANs on routers, how Layer 3 switches perform inter‑VLAN routing, and how Switch Virtual Interfaces (SVIs) operate. I also learned how to troubleshoot SVIs when they show down/down.
Key Concepts Learned
Native VLAN on Routers

Two ways to configure the native VLAN:

    Encapsulation method

    interface g0/0.99
     encapsulation dot1Q 99 native
     ip address 192.168.99.1 255.255.255.0

    Direct IP assignment  
    Assign the native VLAN IP directly to the physical interface.

Important: Native VLANs must match between switches and routers. Mismatches cause traffic leaks or dropped frames. For security, avoid using VLAN 1 as native.
Inter‑VLAN Routing with Layer 3 Switches

    A Layer 3 switch can perform both Layer 2 switching and Layer 3 routing.

    Instead of using a router (ROAS), you configure SVIs (Switch Virtual Interfaces).

    Each VLAN gets its own SVI with an IP address.

    End devices use the SVI IP as their default gateway.

    The switch can then route between VLANs internally, without needing a router for local traffic.

Example:

interface vlan 10
 ip address 192.168.10.1 255.255.255.0
 no shutdown

interface vlan 20
 ip address 192.168.20.1 255.255.255.0
 no shutdown

Default Route from Layer 3 Switch

    To reach external networks (like the internet), the Layer 3 switch needs a default route pointing to the router.

    Example:

ip route 0.0.0.0 0.0.0.0 192.168.99.2

    The router IP on the transit link becomes the next hop.

SVI Troubleshooting

If an SVI shows down/down:

    Ensure the SVI is not shutdown (no shutdown).

    Verify the VLAN exists in the VLAN database.

    Confirm at least one access port is assigned to that VLAN and is active.

    Or ensure the VLAN is carried on an active trunk port.

Without an active port in the VLAN, the SVI will remain down.
Learning Outcomes

    Learned two methods to configure native VLANs on routers.

    Understood how Layer 3 switches perform inter‑VLAN routing using SVIs.

    Practiced configuring SVIs and assigning them as gateways.

    Learned how to set a default route from a Layer 3 switch to a router.

    Troubleshot SVIs showing down/down and identified causes.

Key Takeaways

    Native VLANs must match between devices; avoid VLAN 1 for security.

    Layer 3 switches eliminate the need for ROAS in local routing.

    SVIs act as gateways for VLANs and enable inter‑VLAN routing.

    Default routes on Layer 3 switches point to routers for external connectivity.

    Active ports are required for SVIs to come up.
