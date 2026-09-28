
Purpose of STP
Prevents Layer 2 loops caused by redundant switch connections.
Prevents broadcast storms, MAC address table instability, and duplicate frame forwarding.
Creates a loop-free topology by placing some ports into a non-forwarding state.
Root Bridge Election

I learned how STP elects a Root Bridge for the network.

The Root Bridge is determined by the lowest:

Bridge Priority
MAC Address (used as a tiebreaker)

Once elected:

All ports on the Root Bridge become Designated Ports and remain in the forwarding state.
Every non-root switch selects its best path back to the Root Bridge using a Root Port.
Additional redundant links may become Blocking Ports to prevent loops.
Port Selection Process

I learned how STP decides which ports will forward traffic and which will be blocked.

Factors used include:

Path Cost
Bridge Priority
Port Priority
Port ID
MAC Address

Port roles include:

Root Port (best path toward Root Bridge)
Designated Port (best path for a network segment)
Blocking/Alternate Port (backup path)
STP Port States
Blocking
Does not forward user traffic.
Listens for BPDUs.
Prevents switching loops.
Listening
Begins participating in STP calculations.
Sends and receives BPDUs.
Does not learn MAC addresses yet.
Does not forward traffic.
Learning
Learns MAC addresses and populates the MAC table.
Still does not forward user traffic.
Prepares for the forwarding state.
Forwarding
Fully operational.
Forwards user traffic.
Learns MAC addresses.
Continues processing BPDUs.
Disabled
Administratively shut down or unavailable.
Does not participate in STP.
STP Toolkit Features
PortFast

Configured PortFast on access ports connected to end devices.

Benefits:

Bypasses Listening and Learning states.
Allows end devices to become operational immediately.
Reduces startup delays for PCs, printers, and servers.

Example:

interface fa0/1
spanning-tree portfast
Show more lines
BPDU Guard

Configured BPDU Guard to protect PortFast ports.

Purpose:

Shuts down a port if a BPDU is received.
Helps prevent accidental switch connections on access ports.
Protects the STP topology from unauthorized devices.

Example:

interface fa0/1
spanning-tree bpduguard enable
Show more lines
BPDU Filter

Learned how BPDU Filter suppresses BPDU processing on selected interfaces.

Purpose:

Prevents transmission and reception of BPDUs.
Should be used carefully because it can unintentionally create Layer 2 loops.
Root Guard

Configured Root Guard to prevent unauthorized switches from becoming the Root Bridge.

Purpose:

Maintains the intended Root Bridge.
Places a port into a root-inconsistent state if superior BPDUs are received.

Example:

interface fa0/24
spanning-tree guard root
Show more lines
Loop Guard

Configured Loop Guard to prevent STP failures caused by unidirectional link issues.

Purpose:

Prevents a blocked port from incorrectly transitioning to forwarding.
Protects against loops when BPDUs stop being received unexpectedly.

Example:

interface fa0/24
spanning-tree guard loop
Show more lines

Key Takeaways
STP is critical for preventing Layer 2 loops in switched networks.
The Root Bridge serves as the central reference point for all path calculations.
Root Ports and Designated Ports forward traffic, while redundant paths are blocked.
Understanding port roles and port states is essential for troubleshooting switching issues.
Features such as PortFast, BPDU Guard, Root Guard, BPDU Filter, and Loop Guard provide additional protection and control over STP behavior.
Proper STP design increases network stability, redundancy, and fault tolerance.
