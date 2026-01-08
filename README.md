# Cybersecurity Home Lab

## Overview
This project documents a personal cybersecurity home lab built using VirtualBox.
The lab consists of a Kali Linux attacker machine and a Windows 10 target machine
configured on an isolated host-only network for safe testing and reconnaissance.

## Lab Environment
- Hypervisor: VirtualBox
- Attacker VM: Kali Linux 2025.x
- Target VM: Windows 10
- Host OS: Windows 11

## Network Configuration
- Kali Linux:
  - NAT adapter for internet access
  - Host-only adapter for isolated lab communication
- Windows 10:
  - Host-only adapter only (no internet access)

Both virtual machines reside on the 192.168.56.0/24 subnet.

## Connectivity Testing

Initial connectivity tests were performed using ICMP echo requests.

- Windows successfully pinged the Kali Linux system.
- ICMP traffic from Kali to Windows was initially blocked by Windows Defender Firewall.
- After enabling ICMPv4 echo request rules, bidirectional connectivity was verified.

This demonstrated default host-based firewall protections and controlled access.
## Nmap Scanning

### Host Discovery
Nmap was used to confirm the availability of the Windows target on the
host-only network.

### Basic Port Scan
A basic TCP port scan was performed from the Kali Linux system against
the Windows 10 target.

All scanned ports were reported as filtered, indicating that Windows
Defender Firewall was actively blocking unsolicited inbound connections.
This reflects a hardened default security posture and reduced attack surface.

### Service and OS Detection
Service and OS detection scans returned the same results due to all
ports being filtered, preventing further enumeration.

## Tools Used
- VirtualBox
- Kali Linux
- Windows 10
- Nmap
- Windows Defender Firewall

## Skills Demonstrated
- Virtual machine setup and management
- Network segmentation using host-only networking
- Firewall behavior analysis
- Basic reconnaissance and port scanning
- Security-focused documentation


## Status
This repository is actively updated as I complete new labs.
