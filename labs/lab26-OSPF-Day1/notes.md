OSPF Day 1 Notes
What is OSPF?

Open Shortest Path First (OSPF) is a link-state Interior Gateway Protocol (IGP) used to exchange routing information within an autonomous system.

OSPF Areas

OSPF networks are divided into areas to improve scalability and reduce routing overhead.

Area 0 is the Backbone Area.
All other areas should connect to Area 0.
Router Types

Internal Router

All interfaces belong to the same OSPF area.

Backbone Router

Has at least one interface in Area 0.

Area Border Router (ABR)

Connects Area 0 to one or more non-backbone areas.
Has interfaces in multiple OSPF areas.

Autonomous System Boundary Router (ASBR)

Redistributes routes from another routing protocol or external source into OSPF.
OSPF Neighbor Relationships

Routers can become OSPF neighbors when key parameters match, including:

Area ID
Hello and Dead timers
Authentication settings (if configured)
Network type
Route Types

Intra-Area Routes

Routes learned within the same OSPF area.

Inter-Area Routes

Routes learned from another OSPF area through an ABR.
OSPF Network Statements

Wildcard masks are used to determine which interfaces participate in OSPF.

Example:
router ospf 1
network 192.168.1.0 0.0.0.255 area 0

The wildcard mask identifies which interfaces should have OSPF enabled.

Default Route Advertisement

A default route can be advertised to OSPF neighbors using:
default-information originate

This allows other routers to learn a route of:
0.0.0.0/0

Passive Interfaces

Passive interfaces prevent OSPF neighbor formation while still advertising the connected network.

Example:
passive-interface GigabitEthernet0/0

Useful for:

LAN interfaces with end devices
Interfaces where no OSPF neighbors should exist
OSPF Router ID

Router ID selection priority:

Manually configured Router ID
Highest IP address on a loopback interface
Highest IP address on a physical interface

Example:
router ospf 1
router-id 1.1.1.1


Key Takeaways
OSPF is a link-state IGP.
Uses areas to scale large networks.
Area 0 is the backbone area.
ABRs connect multiple areas.
ASBRs connect OSPF to external routing sources.
Wildcard masks determine which interfaces participate in OSPF.
Passive interfaces stop neighbor formation while still advertising networks.
Router ID priority is:
Manual
Loopback
Physical Interface
Default routes can be advertised with default-information originate.
