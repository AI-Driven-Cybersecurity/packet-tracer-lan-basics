# Simple LAN Simulation: 4 PCs Through a Switch (Cisco Packet Tracer)

A hands-on networking lab built in Cisco Packet Tracer to understand the fundamentals of local network connectivity — cabling, static IP addressing, subnetting, and connectivity verification with `ping`.

## 📌 Overview

This project simulates the simplest possible LAN topology: four PCs connected to a single switch, each assigned a static IP address on the same subnet. The goal was to actually build and verify a working network end-to-end, rather than just reading about how switches and IP addressing work in theory.

## 🧰 Tools Used

- Cisco Packet Tracer
- 1x Switch (2960 series)
- 4x PCs
- Copper Straight-Through cables

## 🖧 Network Topology

The switch sits at the center, with all four PCs cabled directly into it using Straight-Through cables (the correct choice since PC and Switch are different device types).

![Workspace with switch and 4 PCs](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/zc53n84akgnfpjc1eacr.jpg)

![All PCs cabled to the switch — green link lights](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/3gavd3dkr4irfpowbnj3.jpg)

## 🌐 IP Addressing Scheme

| PC | IP Address | Subnet Mask |
|----|-----------|-------------|
| PC0 | 192.168.1.1 | 255.255.255.0 |
| PC1 | 192.168.1.2 | 255.255.255.0 |
| PC2 | 192.168.1.3 | 255.255.255.0 |
| PC3 | 192.168.1.4 | 255.255.255.0 |

All PCs share the same subnet mask so they're on the same `192.168.1.0` network and can communicate directly without needing a router.

<details>
<summary>📷 IP Configuration Screenshots (click to expand)</summary>

![PC0 IP Configuration](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/ocyfagahbtoxo7lrvwrq.jpg)

![PC1 IP Configuration](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/1bobpl4x3av6t48inc6y.jpg)

![PC2 IP Configuration](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/43mc9wh668jctvh0qunm.jpg)

![PC3 IP Configuration](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/qyao7f8rtxbudvd88axy.jpg)

</details>

## ✅ Connectivity Verification

Connectivity was verified by pinging from PC0 to every other PC on the network:

```
ping 192.168.1.2
ping 192.168.1.3
ping 192.168.1.4
```

Every ping returned a successful reply with 0% packet loss.

![Ping PC0 to PC1 successful](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/yn91t2nle4ziv6ps7rut.jpg)

![Ping PC0 to PC2 successful](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/tup78481pogs2v6s2xpy.jpg)

![Ping PC0 to PC3 successful](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/r9lumovf2lj23e9sifm7.jpg)

## 🧠 Key Takeaways

- Switches operate at Layer 2 and forward traffic based on MAC addresses, not IPs — but PCs still need valid IP configuration to communicate meaningfully above that layer.
- Straight-Through cables connect different device types (PC ↔ Switch); Crossover cables connect same device types (Switch ↔ Switch, PC ↔ PC).
- Matching subnet masks are what actually put devices in the same logical network — a green link light only confirms the physical layer, not full connectivity.
- `ping` is the fastest and most reliable way to verify actual network connectivity.

## 🐛 Common Mistakes

| Mistake | Why It Happens | Fix |
|---|---|---|
| Using a Crossover cable instead of Straight-Through | Mixing up when each cable type applies | Different device types = Straight-Through |
| Mismatched subnet masks | Copy-pasting config without double-checking | Verify every PC uses the same mask if they should be on one network |
| Typo in IP address | Manual entry across multiple PCs | Double-check each octet before moving to the next PC |
| Assuming green link light = full connectivity | Confusing physical layer with network layer | Always confirm with `ping`, not just visual cues |
| Forgetting to set Static mode before entering an IP | DHCP is selected by default | Switch to Static first, then fill in the address fields |

## 📖 Full Write-Up

I wrote a full walkthrough of this project on Dev.to, covering the reasoning behind each step in more depth: *(add your Dev.to article link here)*

## 🔭 What's Next

Planning to extend this lab by adding a router into the topology and experimenting with inter-subnet routing between two separate networks.

---

## 🌐 Connect With Me
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/almahmudkhalif/)
[![Dev.to](https://img.shields.io/badge/Dev.to-Articles-black?logo=devdotto)](https://dev.to/almahmudkhalif/)
