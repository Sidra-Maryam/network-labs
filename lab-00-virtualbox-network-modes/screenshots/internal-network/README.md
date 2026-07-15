# Evidence: Mode 5 - Internal Network

This folder contains verification screenshots validating the Internal Network mode behavior.

---

## Core Mechanics Verified

* Pure Software Isolation: Communication is contained entirely within named software boundaries inside the hypervisor engine.
* No Automatic Services: No built-in DHCP server is running on this network segment, which requires manual static IP configuration before any testing can occur.
* Strictest Air-Gap: The external internet, local gateway paths, and the host computer itself are completely locked out of this segment.

---

## Captured Benchmarks

1. manual_ip_assign.png: Shows the explicit configuration of static IP addresses (192.168.100.10 and 192.168.100.20) using terminal commands.
2. inter_vm_success.png: Captures clean, low-latency ping traffic passing strictly between the two configured guest instances once addressing is resolved.
3. host_failure_log.png: Shows Windows PowerShell returning Destination host unreachable errors when trying to target the internal guest IP spaces.

---

## Connectivity Constraints

* Total Isolation: Only virtual machines attached to the exact same named internal network string can communicate.

> [!IMPORTANT]
> Conclusion: Internal Network mode provides the highest layer of containment for sensitive security experiments, at the cost of losing automatic IP assignment and host management tools.
