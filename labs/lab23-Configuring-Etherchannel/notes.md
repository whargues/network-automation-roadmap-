EtherChannel allows multiple physical interfaces to be bundled into a single logical interface called a Port-Channel.

Benefits
Increases available bandwidth by combining links.
Provides redundancy if a member link fails.
Prevents links from being blocked by STP while still allowing multiple links to be utilized.

Without EtherChannel, Spanning Tree Protocol (STP) would block redundant links to prevent switching loops. EtherChannel allows those links to be treated as a single logical connection.

Layer 2 EtherChannel

A Layer 2 EtherChannel operates like a switchport.

Common uses:

Trunk links between switches
Carrying multiple VLANs
Access links (less common)

Layer 3 EtherChannel

A Layer 3 EtherChannel functions as a routed interface.

Characteristics:

No switchport configuration
Assigned an IP address
Used for routing between devices
Does not carry VLAN trunks

Why Use It?

Provides higher bandwidth and redundancy for routed connections between switches and routers.

Example:

Core Switch ↔ Distribution Switch
Distribution Switch ↔ Router
Switch ↔ Firewall
EtherChannel Protocols
LACP (Link Aggregation Control Protocol)
IEEE standard (802.3ad / 802.1AX)
Works between different vendors
Recommended for most deployments

Modes:

Mode	FunctionActive	Actively negotiates EtherChannel
Passive	Waits for LACP packets

Connections that work:

Active + Active Yes 
Active + Passive Yes
Passive + Passive No

PAgP (Port Aggregation Protocol)
Cisco proprietary
Cisco devices only

Modes:

Mode	FunctionDesirable	Actively negotiates
Auto	Waits for negotiation

Connections that work:

Desirable + Desirable Yes
Desirable + Auto Yes
Auto + Auto No


Static EtherChannel
No negotiation protocol is used.
Characteristics:
No LACP or PAgP packets exchanged
Both sides must be configured correctly
Less fault tolerant
Generally not recommended compared to LACP

Load Balancing
EtherChannel does not send a single flow across all links simultaneously.
Instead, traffic is distributed using hashing algorithms.

Examples:

src-ip = hash based on source IP
dst-ip = hash based on destination IP
src-dst-ip = hash using both addresses

