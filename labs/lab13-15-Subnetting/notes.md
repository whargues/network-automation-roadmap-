Day 13–15 – Subnetting, CIDR, VLSM, Bit Borrowing, and Multi‑LAN VLSM Lab
CIDR & Why It Exists

CIDR (Classless Inter‑Domain Routing) was introduced by the IETF in 1993 to replace rigid IPv4 classes and slow down address exhaustion.

CIDR allows:

    Flexible prefix lengths (e.g., /27, /19, /30)

    Efficient IP space usage

    Splitting large networks into smaller subnets

    Aggregation (route summarization)

CIDR completely replaces the old “Class A/B/C” boundaries, but CCNA still teaches classes for historical context.
IPv4 Classes (Review)

    Class A: 0.0.0.0 – 127.255.255.255

    Class B: 128.0.0.0 – 191.255.255.255

    Class C: 192.0.0.0 – 223.255.255.255

    Class D: Multicast

    Class E: Experimental

Companies get IP blocks from IANA → RIRs → ISPs → organizations.
Point‑to‑Point Networks

Router‑to‑router links (WANs) often use:

    /30 (2 usable hosts)

    /31 (special case: 1 usable host each side, no broadcast)

These conserve address space.
Bit Borrowing & Subnet Creation

I learned how to borrow bits from the host portion to create more subnets.

Key rules:

    Borrowing bits increases subnets

    Leaving bits increases hosts

    Formula:

        Subnets = 2n

        Hosts = 2h−2

I practiced determining:

    How many subnets a parent block can be split into

    Which subnet a host belongs to based on its prefix

    How binary boundaries define network increments

Determining a Host’s Subnet

Given an IP and prefix:

    Convert prefix to block size

    Find the network increments

    Identify which range the host falls into

Example:
192.168.5.77/26 → block size 64 → subnet ranges:

    0–63

    64–127

    128–191

    192–255

77 falls in 64–127, so network = 192.168.5.64/26.
VLSM (Variable Length Subnet Masking)

Unlike FLSM (all subnets same size), VLSM lets you create different‑sized networks based on host requirements.

I learned the proper VLSM workflow:
VLSM Steps

    List all required LAN sizes

    Sort from largest → smallest

    Assign the biggest prefix first

    Carve smaller subnets from remaining space

    Continue until all LANs + point‑to‑point links are allocated

    Assign:

        First usable → PC

        Last usable → Router interface

    Configure static routes so all LANs can communicate

    
