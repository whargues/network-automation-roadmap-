Day 9 focused on understanding how switch interfaces operate, how duplex and speed settings affect network performance, and how Cisco devices detect and report interface errors. I also learned how to manually configure interface ranges and interpret output from show ip interface brief, show interface status, and show interfaces.

Switch Interface Columns (show commands)
show ip interface brief

Displays a quick summary of interface status:

    Interface name

    IP address

    Status (up/down)

    Protocol (up/down)

show interface status

Shows operational details:

    Interface

    Description

    Status

    VLAN

    Duplex

    Speed

    Type

These columns help identify mismatches, errors, and misconfigurations.
Duplex & Speed
Duplex Modes

    Full duplex – send & receive simultaneously

    Half duplex – one direction at a time (causes collisions)

Speed

Common speeds:

    10 Mb

    100 Mb

    1 Gb

    10 Gb

Auto‑Negotiation

Devices normally negotiate:

    Speed

    Duplex

If auto‑negotiation is disabled on one side:

    The other device defaults to half duplex

    Speed may drop to 10 or 100 Mb

    Collisions and late collisions occur

    CRC errors increase

    Performance tanks

Hubs

If a hub is introduced:

    Always half duplex

    Collisions are guaranteed

    CSMA/CD becomes active

CSMA/CD (Collision Handling)

Carrier Sense Multiple Access / Collision Detection
Used in half‑duplex Ethernet.

Process:

    Device listens for traffic

    Sends frame

    If collision occurs → jam signal

    Random backoff timer

    Retry transmission

Modern full‑duplex switches do not use CSMA/CD.
Security Risks of Leaving Ports Enabled

Unused switch ports should be:

    Shutdown

    Placed in an unused VLAN

    Labeled with descriptions

Leaving ports active allows:

    Rogue device connections

    Unauthorized network access

Interface Errors (show interfaces)
Common Errors

    Runts – frames smaller than 64 bytes

        Often caused by collisions or duplex mismatch

    Giants – frames larger than 1518 bytes

        Usually MTU issues

    CRC errors – corrupted frames

        Bad cabling, interference, duplex mismatch

    Late collisions – collision after 64 bytes

        Strong sign of duplex mismatch

    Input errors – general receive problems

    Output errors – general transmit problems

    Learning Outcomes

    Understood switch interface status columns and what they represent

    Learned how duplex and speed affect network performance

    Identified problems caused by disabling auto‑negotiation

    Reviewed CSMA/CD and when collisions occur

    Practiced configuring interface ranges for speed/duplex

    Learned how to detect interface errors using show interfaces

    Strengthened understanding of troubleshooting physical layer issues
    MAC flooding attacks

    DHCP spoofing risks
