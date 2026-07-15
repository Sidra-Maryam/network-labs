# Evidence: Mode 1 - Standard NAT

This folder contains verification screenshots validating VirtualBox's default **NAT** mode behavior.

---

## Core Mechanics Verified

* **Isolated Bubbles:** VirtualBox places each VM into its own entirely separate virtual network instance.
* **Identical IPs:** Both Kali Linux and Metasploitable2 are auto-assigned the identical IP address (`10.0.2.15/24`) without collision because their networks are independent.
* **Self-Looping:** Pinging `10.0.2.15` results in a sub-millisecond local loopback response within that specific VM's isolated stack.

---

## Captured Benchmarks

1. **`hypervisor_settings.png`** – Confirms both VMs are set to `Attached to: NAT` in the VirtualBox GUI.
2. **`kali_ifconfig_ping.png`** – Shows Kali's interface at `10.0.2.15` and a successful outbound `ping` to the internet (`8.8.8.8`) translated via the host.
3. **`metasploitable_ifconfig_ping.png`** – Shows Metasploitable2 at `10.0.2.15` with successful independent internet access to `8.8.8.8`.

---

## Connectivity Constraints

* **VM-to-VM:** Hard blocked. No communication path exists between the attacker and target because they do not share a network segment.
* **Host-to-VM:** Inbound routing from the Windows host directly to the guest VMs is completely hidden by default.

> [!IMPORTANT]
> **Conclusion:** Standard NAT mode is unsuitable for penetration testing labs because the attacker machine cannot discover or interact with the target system.
