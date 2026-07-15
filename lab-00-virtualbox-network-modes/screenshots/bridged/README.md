# Evidence: Mode 3 — Bridged Adapter

This folder contains verification screenshots validating the Bridged Adapter mode behavior.

---

## Core Mechanics Verified

* Physical LAN Integration: VirtualBox connects the VM interface directly to the host machine's physical adapter, bypassing internal translation engines.
* Real Subnet Addressing: Both VMs receive IP addresses from the physical network's real DHCP server (192.168.100.203 and 192.168.100.202) instead of a hypervisor pool.
* Flat Network Peers: Guest VMs sit alongside the Windows host as equal nodes on the actual local area network.

---

## Captured Benchmarks

1. hypervisor_settings.png: Confirms both VMs are set to Attached to: Bridged Adapter using the host's active wireless or wired card name.
2. local_dhcp_lease.png: Shows both Kali and Metasploitable2 successfully pulling 192.168.100.x subnet boundaries.
3. bi_directional_ping.png: Displays successful cross-talk pings between the two systems running through the local physical gateway.

---

## Connectivity Constraints

* Real World Exposure: High risk. Because the VMs are full peers on your actual network, they are completely visible to other real devices sharing your local network.

> [!WARNING]
> Conclusion: Bridged mode should be used cautiously when dealing with intentionally vulnerable systems like Metasploitable2 due to the risk of exposure beyond your intended lab boundary.
