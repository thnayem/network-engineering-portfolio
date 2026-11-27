# Network Engineering Portfolio

**Md. Tanvir Hossain**  
Network Administrator | Enterprise Networking | IT Infrastructure Operations

A practical portfolio of network engineering references covering enterprise routing, switching, service-provider edge concepts, GPON access, traffic engineering, connectivity operations and troubleshooting.

## Important context: production experience vs. published material

My real-world, hands-on exposure to live production networks is considerably broader than the examples and notes published in this repository. This repository is only a selected glimpse of that experience; it is not a complete inventory of the networks, devices, incidents, changes or responsibilities I have worked with. More material and lessons are still waiting to be documented.

I do not publish original employer/customer production configurations, raw router or switch backups, credentials, real management addressing, private topology or confidential network information. The content here consists of study notes, learning references, independently prepared lab/demo configurations, troubleshooting exercises, implementation practice and selected lessons from practical work. Production experience is described separately and at a high level. A sample or lab configuration must not be interpreted as an exact configuration taken from, or deployed unchanged in, a live production network.

I can make mistakes, including technical or documentation mistakes. I believe professional responsibility means acknowledging them, checking the evidence, communicating the impact, correcting the issue and learning from the outcome. I aim to approach network changes carefully, prepare a recovery path and take ownership of the work assigned to me.


## Five-minute overview

- **Production experience:** Hands-on involvement in live infrastructure, including remote configuration, upgrades, maintenance and troubleshooting of servers, routers and switches.
- **Engineering coverage:** Multi-vendor routing and switching, BGP, OSPF, VLANs, VRF, PBR, VPN, GRE, IPsec, OSPF over GRE and WAN connectivity.
- **Operational approach:** Impact assessment, evidence-led fault isolation, change planning, backup/rollback preparation, service restoration and post-change verification.
- **Learning approach:** Vendor references, sanitized configuration studies, independent lab examples and troubleshooting notes. I document what I have tested and identify what still needs validation.

## Start here

| Section | What you will find |
|---|---|
| [Platform index](./platforms/) | Vendor and device-family references |
| [Routing](./routing/) | BGP, OSPF, PBR, routing policy and static routing |\n| [Dual-ISP BGP lab](./routing/bgp/dual-isp-traffic-engineering-lab.md) | eBGP, Local Preference, AS-PATH prepending, filtering and failover |
| [Switching](./switching/) | VLANs, trunks, RSTP, ACLs and Nexus references |
| [VPN](./vpn/) | Site-to-site, remote access and IPsec references |
| [Tunnel technologies](./tunnels/) | GRE, IPsec, L2TP, GRE over IPsec and tunnel design |\n| [IKEv2 Site-to-Site IPsec Lab](./tunnels/ipsec-site-to-site-ikev2-lab.md) | IKEv2, ESP, traffic selectors, NAT-T, verification and troubleshooting |
| [Connectivity and DC/DR operations](./connectivity-operations/) | Multi-site NTTN transport, provider coordination and DC/DR connectivity |
| [Operations case studies](./case-studies/) | Sanitized operational examples and lessons |
| [Troubleshooting scenarios and demos](./case-studies/troubleshooting-scenarios.md) | Fault isolation, incident updates and change safety |
| [Network architecture](./network-architecture/) | Logical topology and segmentation examples |
| [GPON/OLT operations](./gpon-olt/) | Access-network troubleshooting |
| [Troubleshooting](./troubleshooting/) | Operational fault-isolation references |

## Selected technical coverage

### Juniper
- [MX204](./platforms/juniper/mx204/) - logical systems, firewall filters, routing policy and service forwarding.
- [MX240](./platforms/juniper/mx240/) - logical systems, logical tunnels, BGP policy and chassis patterns.

### Cisco
- [ASR 920](./platforms/cisco/asr920/) - EVC service instances, bridge domains, BDI, VRF-aware BGP, route policy and QoS.
- [7606-S](./platforms/cisco/7606s/) - VRFs, VLAN handoffs, EtherChannel, BGP, PBR and QoS.
- [Nexus core](./platforms/cisco/nexus-core-switch/) - MST, VLAN, LACP, trunk and SPAN references.
- [Nexus 3000](./platforms/cisco/nexus-3k-cybernet-core/) - source-derived switching reference and STP/RSTP design alternative.

### MikroTik
- [RouterOS 6/7](./platforms/mikrotik/) - CCR routing, BGP, OSPF, PBR, NAT, QoS and CRS switching.
- [CRS309](./platforms/mikrotik/crs309/) - VLAN-aware bridge, tagged trunks and bridge VLAN membership.

### Huawei, Arista and BDCOM
- [Huawei MA5800-X7](./platforms/huawei/) - GPON profiles, DBA, GEM mapping, service VLANs and ONT operations.
- [Arista DCS-7050S-52](./platforms/arista/dcs-7050s-52/) - EOS switching, VLANs, trunks, MSTP and LACP.
- [BDCOM access and POP switches](./platforms/bdcom/) - VLAN handoffs, trunk allow-lists, RSTP and uplinks.

## Production operations

My practical experience includes remote administration and troubleshooting of production routers, switches and servers; routing and switching operations; multi-site connectivity over NTTN links; OSPF routing over GRE; VPN and tunnel support; and DC/DR connectivity coordination.

Operational work includes fault isolation, provider follow-up, maintenance planning, configuration review, backup/rollback preparation and post-change service checks. These statements describe areas of involvement, not a claim that every configuration in this repository was deployed unchanged in production.

## How to read the material

Every example should be read with its evidence label:

- **Production experience:** A description of work I have been involved in, with confidential details removed.
- **Sanitized reference:** A reduced, anonymized or source-derived technical reference. It is not a raw backup or a deployment-ready file.
- **Lab/demo:** An independently authored example used for learning or explaining a design. It is not proof of production deployment.
- **Design note:** Explains topology, packet flow, trade-offs and dependencies.
- **Verification note:** Shows what to check and what a healthy result should look like. Hardware/parser validation is claimed only when actually performed.

All public examples use fictional identifiers and documentation-only addressing where needed. Check platform, software release, feature support and change requirements before adapting any configuration.

## Troubleshooting and change discipline

For a network issue, I start by confirming the affected service and scope. I check physical state and interface counters, then VLAN/Layer 2, routing, tunnel or VPN state, policy, MTU and the remote endpoint as relevant. I compare the current state with the last known good state, keep evidence, and avoid making unrelated changes during an incident.

For planned work, I review dependencies, capture a baseline, arrange an approved window, prepare a rollback path and verify service from both the network and user/service perspective.

## Documentation standard

New and updated technical pages follow the shared structure in [DOCUMENTATION-GUIDE.md](./DOCUMENTATION-GUIDE.md): purpose and scope, evidence type, topology/packet flow, sanitized configuration, explanation, troubleshooting, verification, rollback and lessons learned.

The repository is organized by platform/vendor and by technical domain. See [PORTFOLIO-STRUCTURE.md](./PORTFOLIO-STRUCTURE.md) for placement and publication rules.

## Security and limitations

Never publish raw backups, credentials, keys, SNMP communities, customer/provider details, real management addressing, private topology or employer documents. Review the complete diff and repository history before publishing.

No vendor parser or physical-device validation is claimed unless a specific page records the test, platform and release.
