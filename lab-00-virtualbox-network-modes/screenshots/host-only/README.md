# Evidence: Mode 4 - Host-Only Adapter

This folder contains verification screenshots validating the Host-Only Adapter mode behavior.

---

## Core Mechanics Verified

* Isolated Loopback: VirtualBox provisions an isolated virtual switch shared strictly between the host machine and attached guest nodes.
* Automatic Management: Unlike standard internal configurations, this mode includes a hypervisor-managed DHCP server, assigning IPs like 192.168.56.102 and 192.168.56.101 automatically.
* Host Visibility: The host machine can directly reach and manage the VMs on this private link, which distinguishes it from an internal network setup.

---

## Captured Benchmarks

1. host_ipconfig.png: Shows the Windows host machine's virtual loopback adapter configuration inside PowerShell.
2. host_to_vm_ping.png: Captures successful ping responses sent directly from the Windows host terminal to both running guest systems.
3. internet_failure.png: Displays an immediate Network is unreachable error message when attempting to ping 8.8.8.8 from inside a VM.

---

## Connectivity Constraints

* Outbound Access: Hard blocked. No default route out to the public internet exists on this network segment.

> [!NOTE]
> Conclusion: Host-Only mode is well suited for sandbox testing environments where the host machine still requires administrative visibility into the lab.
