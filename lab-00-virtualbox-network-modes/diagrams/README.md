# Architecture Diagrams

This directory houses the custom system topology diagrams detailing the packet flow, routing logic, and boundary layers for each of the five hypervisor networking configurations. 

These architectural visuals visually map how the guest VMs (Kali Linux and Metasploitable2) interact with the VirtualBox engine, the Windows host, and external gateways.



## 🎛️ Mapping Summary

| Diagram File | Subnet Scope | External Internet Path | Host Visibility | IP Management Type |
| :--- | :--- | :--- | :--- | :--- |
| `nat.png` | Isolated Per VM Bubble | Enabled (NAT Translate) | Hidden / Not Applicable  | Automatic (Duplicated Defaults) |
| `nat-network.png`| Shared Subnet Segment  | (NAT Translate) | Hidden by Default | Automatic (Hypervisor Pool) |
| `bridged.png` | External Physical LAN  | Enabled (Direct Gateway)  | Full LAN Peer Access  | Automatic (Local LAN DHCP)  |
| `host-only.png` | Isolated Loopback Subnet | Hard Blocked (No Route)  | Full Direct Host Visibility  | Automatic (Host Virtual Switch) |
| `internal-network.png`| Named Software Network | Hard Blocked (No Route)  | Hard Blocked (No Route) | Manual (Static Input Required) |

> [!TIP]
> All visual assets listed here match the exact technical configurations and data frames analyzed in the primary technical laboratory report file: [VirtualBox_Network_Mode.pdf](../VirtualBox_Network_Mode.pdf).
