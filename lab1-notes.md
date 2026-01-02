# Lab 1: Basic Network Security Lab

## Objective
To create an isolated virtual network and observe how basic security
controls affect system visibility and access.

## Environment
- VirtualBox
- Windows 10 VM
- Ubuntu Linux VM
- Kali Linux VM

## Network Configuration
- Internal Network
- No external internet access

## Steps Taken
1. Created three virtual machines in VirtualBox
2. Configured network adapters to Internal Network
3. Enabled Windows Firewall
4. Performed basic reconnaissance from Kali Linux
5. Reviewed logs on Ubuntu

## Observations
- Windows firewall reduced visible open ports
- Internal network prevented external access
- System logs reflected connection attempts

## What I Learned
- How virtual networks isolate systems
- How firewall rules impact reconnaissance
- The importance of monitoring logs

## Next Improvements
- Add packet capture with Wireshark
- Test different firewall rule configurations
