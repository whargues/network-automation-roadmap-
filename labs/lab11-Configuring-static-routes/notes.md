Day 11 Lab Notes – Routing Fundamentals, Static Routes, Packet Flow, Proxy ARP, and Default Routes

Overview

Day 11 was a major milestone in CCNA journey. I learned what routing is, how routers make forwarding decisions, how to read routing tables, how to configure static routes, how packets flow through a multi‑router network, and how default routes work. I also explored Proxy ARP and interface exit behaviors.

What Routing Is

Routing is the process of forwarding packets between different networks. Routers use routing tables to decide where packets should go.

Routing tables contain:

Codes that identify route types

Destination networks

Subnet masks

Next‑hop IPs or exit interfaces

Administrative distance and metrics

Routing Table Codes

I learned the most important codes for CCNA:

C – Connected: Automatically created when an interface is configured with an IP address and is up.

L – Local: A /32 route automatically created for the exact IP address assigned to an interface.

S – Static: A route manually configured by the administrator.

Connected and Local routes appear without any configuration beyond assigning an IP address.

Routing Fundamentals

Routers forward packets based on:

Longest prefix match

Destination IP address

Next‑hop IP or exit interface

Routers do not change source or destination IP addresses.

Static Route Configuration

I configured three routers with static routes so workstations on different networks could communicate.

Static Route Format

ip route <destination-network> <mask> <next-hop-IP>

Example:

ip route 10.10.20.0 255.255.255.0 192.168.1.2

Static Route Using Exit Interface

ip route <destination-network> <mask> <exit-interface>

Example:

ip route 10.10.20.0 255.255.255.0 g0/1

Static Route Using Exit Interface + Next Hop

ip route <destination-network> <mask> <next-hop-IP> <exit-interface>

I practiced all three methods.

Packet Flow and Encapsulation

I learned how packets move through routers:

Source and destination IP stay the same end‑to‑end.

Source and destination MAC change at every hop.

Each router decapsulates the frame, checks the IP header, and re‑encapsulates the packet with a new MAC pair.

This is the core of how Layer 2 and Layer 3 interact.

Proxy ARP

I learned how Proxy ARP allows a router to respond to ARP requests on behalf of another network.

Key points:

Used when hosts think a destination is on the same subnet but it is not.

Router replies with its own MAC address.

Router forwards the packet to the correct network.

This ties into how exit interfaces behave when static routes use interface‑based forwarding.

Default Routes

Default routes are used when no other route matches.

Default Route Format

ip route 0.0.0.0 0.0.0.0 <next-hop-IP>

Routing Table Code

S tatic route

Asterisk (*) indicates the default route

Default routes are used to send traffic toward the internet or an upstream router.

Learning Outcomes

Understood routing fundamentals and routing table structure

Learned the meaning of C, L, and S route codes

Configured static routes using next hop, exit interface, and combined methods

Observed packet flow and MAC/IP behavior across multiple routers

Learned how Proxy ARP works and why it matters

Configured and identified default routes in routing tables
