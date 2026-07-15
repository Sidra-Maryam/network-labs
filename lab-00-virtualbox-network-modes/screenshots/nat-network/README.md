# Evidence: Mode 2 - NAT Network

This folder contains verification screenshots validating the NAT Network mode behavior.

---

## Core Mechanics Verified

* Shared Subnet: VirtualBox creates a single shared virtual network that multiple VMs can join simultaneously, backed by one shared DHCP server.
* Distinct IPs: Kali and Metasploitable2 receive different addresses on the same subnet (10.0.2.15 and 10.0.2.3) rather than identical addresses, drawing from the same pool.
* True Network Path: Direct communication between the two VMs succeeds with measurably higher latency than a local loopback, proving traffic traverses a genuine network segment.

---

## Captured Benchmarks

1. hypervisor_settings.png: Confirms both VMs are set to Attached to: NAT Network in the VirtualBox GUI.
2. kali_ping_target.png: Shows Kali's interface at 10.0.2.15 and a successful ping connection to Metasploitable2 at 10.0.2.3.
3. metasploitable_ping_external.png: Shows Metasploitable2 running a successful ping to 8.8.8.8, confirming independent internet access.

---

## Connectivity Constraints

* VM to VM: Fully enabled. Both machines can discover and interact with each other directly.
* Host to VM: Hidden by default. The host cannot naturally route into this network segment without port forwarding rules.

> [!NOTE]
> Conclusion: NAT Network mode is ideal for standard multi-machine labs because it allows inter-vm communication while preserving independent internet access.
