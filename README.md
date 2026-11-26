# Network Engineering Portfolio

**Md. Tanvir Hossain**  
Network Administrator | Enterprise Networking | IT Infrastructure Operations

This repository is a collection of network engineering examples drawn from my hands-on work and technical practice. It covers routing, switching, service separation, traffic policy, and day-to-day network operations.

I have rewritten the public examples for documentation and review. They use fictional identifiers and documentation-only addresses. They are not raw device backups, and they should not be pasted into a live network without checking the platform, software release, dependencies, and intended design.

## Main platform examples

- [Cisco 7606-S](./platforms/cisco/7606s/) - VRFs, BGP, VLAN handoffs, EtherChannel, PBR, QoS, and Layer 2 controls
- [Juniper MX204](./platforms/juniper/mx204/) - logical systems, routing policy, firewall filters, and service forwarding
- [Juniper MX240](./platforms/juniper/mx240/) - logical systems, logical tunnels, BGP policy, and chassis configuration patterns
- [MikroTik RouterOS v7](./platforms/mikrotik/) - VLAN-aware bridging and OSPF lab example

## Technical areas

| Area | Topics |
|---|---|
| Routing | BGP, OSPF, static routing, PBR, routing policy |
| Switching | VLANs, trunks, PVST/RSTP, ACLs |
| Platforms | Cisco IOS/NX-OS, Juniper Junos, MikroTik RouterOS, Huawei VRP, Arista EOS |
| Traffic engineering | Prefix filters, route-maps, policing, QoS |
| Network security | Firewall filters, ACLs, management-plane controls |
| Access networks | GPON, OLT/ONU operations, fiber troubleshooting |
| Operations | Fault isolation, verification, change safety, rollback |

## Repository guide

### Network architecture
- [Network architecture notes](./network-architecture/)

### Routing
- [Routing overview](./routing/)
- [BGP](./routing/bgp/)
- [BGP policy](./routing/bgp-policy/)
- [OSPF](./routing/ospf/)
- [Policy-Based Routing](./routing/pbr/)
- [Routing policy](./routing/policy/)
- [Static routing](./routing/static-routing/)

### Switching
- [Switching overview](./switching/)
- [VLAN and trunk example](./switching/vlan/)
- [RSTP](./switching/rstp/)
- [ACL example](./switching/acl/)
- [Nexus example](./switching/nexus/)

### Operations and reference material
- [GPON/OLT operations](./gpon-olt/README.md)
- [Troubleshooting runbook](./troubleshooting/README.md)
- [Reference dates and archive notes](./reference-dates/)
- [Security policy](./SECURITY.md)
- [Production demonstration scope](./PRODUCTION-IMPLEMENTATIONS.md)

## About the examples

The Cisco 7606-S, Juniper MX204, and Juniper MX240 sections are separate platform references. Some files explain selected implementation patterns; others are independently written lab exercises. Each directory describes its own scope and limitations.

I have not represented these files as vendor-certified configurations or as configurations validated on a live device. Check syntax and feature support against the exact platform and software release, then test in an isolated lab.

## Contact

- GitHub: [thnayem](https://github.com/thnayem)
- LinkedIn: [Md. Tanvir Hossain](https://www.linkedin.com/in/thnayem/)
