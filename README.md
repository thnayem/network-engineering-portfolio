# Network Engineering Portfolio

**Md. Tanvir Hossain**  
Network Administrator | Enterprise Networking | IT Infrastructure Operations

A practical portfolio of network engineering references covering enterprise routing, switching, service-provider edge concepts, GPON access, traffic engineering, and infrastructure operations.

The repository is organized in two complementary ways:

- **By platform/vendor** for complete device-family references and source-derived configuration studies.
- **By technical domain** for reusable concepts such as BGP, OSPF, VLANs, RSTP, PBR, ACLs, VPNs, and routing policy.

All public examples are sanitized or independently authored for documentation. They use fictional identifiers and documentation-only addressing. Source-derived references are reduced excerpts, not raw backups. Lab examples are not evidence of production deployment. No file should be pasted into a live network without checking dependencies, platform support, software release, and change/rollback requirements.

---

## Start here

| Section | What you will find |
|---|---|
| [Platform index](./platforms/) | Vendor and device-family references |
| [Routing](./routing/) | BGP, OSPF, PBR, routing policy, static routing |
| [Switching](./switching/) | VLANs, trunks, RSTP, ACLs, Nexus labs |
| [VPN](./vpn/) | Site-to-site, remote-access, IPsec, SSL/TLS VPN, design and troubleshooting |
| [Tunnel technologies](./tunnels/) | GRE, IPsec, L2TP, GRE over IPsec, tunnel design |
| [Network architecture](./network-architecture/) | Logical topology and segmentation examples |
| [GPON/OLT operations](./gpon-olt/) | Vendor-neutral access-network troubleshooting |
| [Troubleshooting](./troubleshooting/) | Operational fault-isolation references |
| [Reference dates](./reference-dates/) | Archive provenance and documentation dates |

## Selected Technical Portfolio

### Juniper
- [MX204](./platforms/juniper/mx204/) - logical systems, firewall filters, routing policy, and service forwarding.
- [MX240](./platforms/juniper/mx240/) - logical systems, logical tunnels, BGP policy, and chassis patterns.

### Cisco
- [ASR 920](./platforms/cisco/asr920/) - EVC service instances, bridge domains, BDI, VRF-aware BGP, route policy, and QoS.
- [7606-S](./platforms/cisco/7606s/) - VRFs, VLAN handoffs, static EtherChannel, BGP, PBR, QoS, and Layer 2 controls.
- [Nexus core switch, NX-OS 7.0(3)I4(3)](./platforms/cisco/nexus-core-switch/) - source-derived MST, VLAN, LACP, trunk, and SPAN reference.
- [Nexus 3000 core, NX-OS 7.0(3)I4(6)](./platforms/cisco/nexus-3k-cybernet-core/) - separate source-derived MST reference and STP/RSTP design alternative.

### MikroTik
- [RouterOS 6/7](./platforms/mikrotik/) - CCR routing references, RouterOS v6/v7 equivalents, BGP, OSPF, PBR, NAT, QoS, and CRS309 switching.
- [CRS309](./platforms/mikrotik/crs309/) - RouterOS 6.48.2 VLAN-aware bridge, tagged trunks, and bridge VLAN membership.

### Huawei
- [MA5800-X7](./platforms/huawei/) - GPON profiles, DBA, GEM mapping, service VLANs, ONT operations, and management.

### Others
- [Arista DCS-7050S-52](./platforms/arista/dcs-7050s-52/) - EOS 4.18.11M, VLANs, trunks, MSTP, LACP, and management controls.
- [BDCOM access and POP switches](./platforms/bdcom/) - VLAN handoffs, trunk allow-lists, RSTP, aggregation, and 10G uplinks.

## Technical domains

| Domain | Coverage |
|---|---|
| Routing | BGP, OSPF, static routing, PBR, route filtering and policy |
| Switching | VLANs, access/trunk ports, STP/RSTP/MSTP, LACP, ACLs |
| VPN and tunneling | Site-to-site, remote access, IPsec, SSL/TLS VPN, GRE, L2TP, GRE over IPsec |
| Traffic engineering | Prefix-lists, route-maps, communities, policing, QoS/PCQ |
| Network security | ACLs, firewall filters, VPN security, management-plane controls, safe publication |
| Access networks | GPON, OLT/ONU lifecycle, optical fault isolation |
| Operations | Verification, fault isolation, change safety, rollback |

For vendor-specific examples, start from the [platform index](./platforms/). For protocol-focused study, explore [Routing](./routing/), [Switching](./switching/), [VPN](./vpn/), and [Tunnel technologies](./tunnels/).

## How to read the examples

Each directory README describes its source, scope, software release, sanitization, and validation boundary where known.

- **Source-derived reference:** a reduced and sanitized study of a supplied configuration. It is not a complete export or deployment-ready configuration.
- **Lab example:** an independently authored example used to explain a feature or design pattern.
- **Design note:** explains topology, packet flow, trade-offs, or control placement.
- **Verification/rollback note:** lists checks and operational safeguards that should be adapted to the target environment.

No vendor parser or physical-device validation is claimed unless a directory explicitly says otherwise. Validate syntax and feature support on the exact hardware and software release before use.

## Repository standards

- [Portfolio structure and navigation guide](./PORTFOLIO-STRUCTURE.md)
- [Security policy](./SECURITY.md)
- [Production implementation scope](./PRODUCTION-IMPLEMENTATIONS.md)

**Security note:** this is a public repository. Never add raw backups, credentials, customer or provider details, real management addressing, subscriber records, private topology, or employer documents without explicit authorization. Review the complete diff and repository history before publishing.
