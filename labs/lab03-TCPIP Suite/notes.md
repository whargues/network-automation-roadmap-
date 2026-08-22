Day 3 Lab Notes – TCP/IP Suite and Packet Flow

Overview

Focused on the TCP/IP suite and observed how it operates in a simulated network environment. The lab was pre‑built, allowing me to run simulations and analyze packet flows across different devices.

Key Activities

Reviewed TCP/IP suite layers: Application, Transport, Internet, and Network Access.

Mapped protocols to layers:

Application: HTTP, DNS

Transport: TCP, UDP

Internet: IP, OSPF

Network Access: Ethernet, ARP

Ran simulations in Cisco Packet Tracer to visualize traffic.

Observed encapsulation/decapsulation as packets moved between devices.

Network Topology

Devices included: SRV1 (Server), PC1 (Client), SW1 & SW2 (Switches), R1 & R2 (Routers).

Addressing scheme:

192.168.1.0/24 network connected to PC1 and SRV1.

10.0.0.0/24 network connecting R1 and R2.

R1 acted as the gateway between the two networks.

Protocol Observations

Spanning Tree Protocol (STP) was active on switches.

OSPF routing was observed between routers.

ARP requests/replies resolved MAC addresses.

HTTP traffic generated at Layer 7 for testing.

Learning Outcomes

Reinforced the difference between OSI model (conceptual) and TCP/IP suite (real-world implementation).

Saw how protocols are layered and interact in live traffic.

Understood how simulation tools help visualize packet flow and protocol behavior.

Next Steps

Practice deeper analysis of routing protocols (OSPF, EIGRP).

Generate more diverse Layer 7 traffic (DHCP).

Document packet flow step‑by‑step for troubleshooting reference.

Summary: Day 3 solidified understanding of the TCP/IP suite by connecting theory to practice. The lab demonstrated how protocols operate across layers and how simulation tools reveal packet behavior in a network.
