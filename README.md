# Network Engineering Portfolio

**Md. Tanvir Hossain**  
Network & Infrastructure Administrator | Enterprise and ISP Networks

I keep my network notes here. Some come from problems I have dealt with at work; others come from things I wanted to understand better, lab setups I tested, or mistakes that sent me back to the documentation. I work across routing, switching, ISP connectivity, GPON, VPNs, tunnels and multi-site networks.

My production work goes further than these public pages. I have configured, maintained, upgraded and troubleshot live routers, switches and servers, including remote work across different environments. I cannot publish company configurations, customer details, device backups or internal diagrams. What I can share is how I approach a problem, what I have learned and examples that are safe to make public. Not every example here is a production configuration.

I do not get everything right the first time. Sometimes a command behaves differently on another release; sometimes the first theory is wrong. I try to check the evidence, understand the impact, test carefully and write down what I learned. Before a risky change, I want to know how I will verify it and how I can back out if needed.

## Repository guide

| Section | What it covers |
|---|---|
| [Platforms](./platforms/) | Vendor and device-family notes |
| [Routing](./routing/) | BGP, OSPF, PBR, routing policy and static routing |
| [Dual-ISP BGP lab](./routing/bgp/dual-isp-traffic-engineering-lab.md) | eBGP, Local Preference, AS-PATH prepending, filtering and failover |
| [Switching](./switching/) | VLANs, trunks, RSTP, ACLs and Nexus references |
| [VPN](./vpn/) | Site-to-site, remote access and IPsec |
| [Tunnels](./tunnels/) | GRE, IPsec, L2TP and GRE over IPsec |
| [IKEv2 Site-to-Site IPsec Lab](./tunnels/ipsec-site-to-site-ikev2-lab.md) | IKEv2, ESP, traffic selectors, NAT-T and troubleshooting |
| [Connectivity and DC/DR operations](./connectivity-operations/) | NTTN transport, provider coordination and DC/DR connectivity |
| [Case studies](./case-studies/) | Sanitized operational examples and lessons |
| [Troubleshooting scenarios](./case-studies/troubleshooting-scenarios.md) | Fault isolation, incident updates and change safety |
| [Network architecture](./network-architecture/) | Logical topology and segmentation examples |
| [GPON/OLT operations](./gpon-olt/) | Access-network troubleshooting |
| [Troubleshooting](./troubleshooting/) | Fault-isolation notes |

## Platforms and examples

### Juniper
- [MX204](./platforms/juniper/mx204/) - logical systems, firewall filters, routing policy and service forwarding.
- [MX240](./platforms/juniper/mx240/) - logical systems, logical tunnels, BGP policy and chassis patterns.

### Cisco
- [ASR 920](./platforms/cisco/asr920/) - EVC service instances, bridge domains, BDI, VRF-aware BGP, route policy and QoS.
- [7606-S](./platforms/cisco/7606s/) - VRFs, VLAN handoffs, EtherChannel, BGP, PBR and QoS.
- [Nexus core](./platforms/cisco/nexus-core-switch/) - MST, VLAN, LACP, trunk and SPAN references.
- [Nexus 3000](./platforms/cisco/nexus-3k-cybernet-core/) - switching references and STP/RSTP design notes.

### MikroTik
- [RouterOS 6/7](./platforms/mikrotik/) - CCR routing, BGP, OSPF, PBR, NAT, QoS and CRS switching.
- [CRS309](./platforms/mikrotik/crs309/) - VLAN-aware bridge, tagged trunks and bridge VLAN membership.

### Huawei, Arista and BDCOM
- [Huawei MA5800-X7](./platforms/huawei/) - GPON profiles, DBA, GEM mapping, service VLANs and ONT operations.
- [Arista DCS-7050S-52](./platforms/arista/dcs-7050s-52/) - EOS switching, VLANs, trunks, MSTP and LACP.
- [BDCOM access and POP switches](./platforms/bdcom/) - VLAN handoffs, trunk allow-lists, RSTP and uplinks.

## Production work

My practical work has included remote administration and troubleshooting of production routers, switches and servers; routing and switching support; multi-site connectivity over NTTN links; OSPF routing over GRE; VPN and tunnel support; and DC/DR connectivity coordination.

Depending on the issue, I may be checking interface state and counters, tracing a routing problem, reviewing VLAN or trunk settings, checking tunnel health, coordinating with a provider or arranging a maintenance window. I try to capture a baseline, keep a backup and agree on a recovery plan before a risky change.

These are areas of work I have been involved in. They do not mean every example in this repository is a production configuration.

## How to read the examples

- **Production experience:** A high-level description of work I have been involved in. Sensitive details are left out.
- **Sanitized reference:** A reduced or anonymized technical reference, not a raw device backup.
- **Lab/demo:** An independently prepared example for learning or demonstration.
- **Design note:** An explanation of topology, traffic flow, dependencies or design choices.
- **Verification note:** Commands and checks to help confirm a result. I only claim a test was run when the page says what was tested and on which platform/release.

Please check the device model, software release and feature support before using any example. A command that works on one platform or release may not work on another.

## Troubleshooting and change work

I normally start by asking what service is affected, when the problem began and whether anything changed recently. Then I narrow it down: physical link, interface errors, VLAN and Layer 2, routing, tunnel or VPN, policy, MTU, remote endpoint or provider path. I avoid changing several unrelated things at once because that makes it harder to know what fixed the issue.

For planned work, I want a clear scope, an agreed window, a backup or baseline, a rollback option and checks that prove the service is back. A green interface alone does not always mean the application or user service is working.

## Documentation

New and updated pages use the [documentation guide](./DOCUMENTATION-GUIDE.md). I try to explain what a page is for, which environment it applies to, what I tried, what happened and how I checked the result. If something is only a lab example or still needs testing, I say so.

See [portfolio structure](./PORTFOLIO-STRUCTURE.md) for where new material belongs.

## Related portfolios

- [System & Server Administration](https://github.com/thnayem/system-server-virtualization-portfolio)
- [Enterprise IT Operations](https://github.com/thnayem/enterprise-it-operations-portfolio)
- [GitHub profile](https://github.com/thnayem)
- [LinkedIn](https://www.linkedin.com/in/thnayem/)

## Security

Do not publish raw backups, passwords, keys, SNMP communities, customer/provider information, real management addresses, private topology or employer documents. Review screenshots, configuration snippets and the full Git diff before committing.

Maintained by [Md. Tanvir Hossain](https://github.com/thnayem) · [LinkedIn](https://www.linkedin.com/in/thnayem/)
