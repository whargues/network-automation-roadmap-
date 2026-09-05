
Day 11 – Static Route Troubleshooting Lab Notes

Overview

This lab expanded on routing fundamentals by focusing on troubleshooting static routes and correcting misconfigurations across multiple routers. After identifying and fixing three issues, full connectivity was restored, allowing successful communication between hosts on different networks.

Issues Found & Fixes Applied

1. Incorrect Interface IP Address

Problem: One router’s interface was configured with the wrong IP: 192.168.12.3 instead of 192.168.12.2.

Impact: Static routes pointing to 192.168.12.2 failed because the next hop didn’t exist.

Fix: Corrected the interface IP to 192.168.12.2.

2. Static Route Using Wrong Exit Interface

Problem: A static route for 192.168.3.0/24 was configured using exit interface g0/0 instead of g0/1.

Impact: Router attempted to forward traffic out the wrong interface, breaking connectivity.

Fix: Reconfigured the static route to use the correct exit interface g0/1.

3. Wrong Interface Address on g0/0

Problem: Another router had g0/0 configured as 192.168.23.3 instead of 192.168.13.3.

Impact: Router advertised and routed traffic for the wrong network, causing mismatched paths.

Fix: Corrected the interface IP to 192.168.13.3.

Result

After applying all three fixes:

Static routes aligned with correct next hops and interfaces.

Interfaces matched the intended network design.

Routing tables updated properly.

End-to-end connectivity was restored.

Verification: A ping from 192.168.1.1 to 192.168.3.1 succeeded, confirming full path restoration.

Key Takeaways

Always verify interface IPs before troubleshooting static routes.

Exit interface vs next hop matters — wrong interface = dead route.

Routing tables reflect connected networks; mismatched IPs break static routes.

Use show ip route, show ip interface brief, and show run interface to identify issues.
