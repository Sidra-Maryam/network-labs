# Lab 00 – VirtualBox Network Mode Comparison

## Objective

Compare the five VirtualBox networking modes and evaluate how they affect:

- VM-to-VM communication
- Internet connectivity
- Host-to-VM communication
- IP address assignment
- Network isolation

## Environment

- Windows 11
- Oracle VirtualBox 7.2
- Kali Linux 2026.2
- Metasploitable2

## Network Modes Tested

- NAT
- NAT Network
- Bridged Adapter
- Host-only Adapter
- Internal Network

## Key Findings

- NAT isolates each VM while providing internet access.
- NAT Network allows VM-to-VM communication while retaining internet access.
- Bridged Adapter places VMs directly on the physical network.
- Host-only Adapter enables communication between the host and VMs without internet access.
- Internal Network provides complete isolation, including from the host.

## Files

- **VirtualBox_Network_Mode.pdf** – Complete lab report
- **diagrams/** – Architecture diagrams
- **screenshots/** – Experimental evidence

## Skills Demonstrated

- VirtualBox Networking
- TCP/IP
- DHCP
- Static IP Configuration
- ICMP Testing
- Network Isolation
- Network Troubleshooting
