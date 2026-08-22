Day 4 Lab Notes – Cisco CLI Basics

Overview

Day 4 focused on learning the fundamentals of the Cisco IOS CLI, including navigation, configuration modes, and password security.

Key Activities

Command discovery: Practiced using ? to list available commands and syntax options.

CLI modes:

User EXEC mode → limited monitoring commands.

Privileged EXEC mode → advanced commands (enable).

Global configuration mode → system‑wide changes (configure terminal).

Show commands:

show running-config → current active configuration.

show startup-config → saved configuration in NVRAM.

Saving configs: Used copy running-config startup-config to persist changes.

PuTTY setup:

Configured serial settings (9600 baud, 8 data bits, no parity, 1 stop bit).

Connected via RJ‑45 console port or mini‑USB rollover cable.

Password security:

Set plain text passwords.

Enabled service password-encryption → Type 7 encryption.

Configured enable secret → Type 5 (MD5) encryption for stronger protection.

Learning Outcomes

Understood differences between running vs startup configs.

Learned how to navigate CLI modes and discover commands quickly.

Practiced secure password configuration with encryption.

Gained confidence in setting up PuTTY console connections and settings.

Next Steps

Explore interface configuration commands (assign IPs, enable ports).

Practice VLAN configuration and trunking.

Document password policies and best practices for lab environments.
