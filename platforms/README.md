# Platform Index

I have grouped the device notes by vendor so it is easier to find the right model and software family. A Cisco IOS example and a Juniper Junos example are not interchangeable, and even devices from the same vendor can behave differently across releases.

My production work has involved remote configuration, planned upgrades, maintenance and troubleshooting of live routers, switches and servers. The public files are shortened or independently prepared examples. They are not full backups of the equipment I have worked on.

| Vendor | Device/reference | Scope |
|---|---|---|
| [Cisco](./cisco/) | [ASR 920](./cisco/asr920/), [7606-S](./cisco/7606s/), [Nexus core switch](./cisco/nexus-core-switch/), [Nexus 3000 core](./cisco/nexus-3k-cybernet-core/) | IOS/IOS XE, NX-OS, EVC, VRF, BGP, switching |
| [Arista](./arista/) | [DCS-7050S-52](./arista/dcs-7050s-52/) | EOS, VLANs, MSTP, LACP |
| [Juniper](./juniper/) | [MX204](./juniper/mx204/), [MX240](./juniper/mx240/) | Junos, logical systems, routing policy, filters |
| [MikroTik](./mikrotik/) | [CCR references](./mikrotik/), [CRS309](./mikrotik/crs309/) | RouterOS 6/7, BGP, OSPF, PBR, NAT, QoS, VLAN bridge |
| [BDCOM](./bdcom/) | [Access switch](./bdcom/access-switch/), [POP switch](./bdcom/pop-switch/) | VLAN handoffs, trunks, RSTP, aggregation |
| [Huawei](./huawei/) | [MA5800-X7](./huawei/) | GPON, DBA, ONT profiles, GEM mapping, service VLANs |

## Operational lifecycle

- **Configuration:** baseline review, interface/service configuration, routing and switching policy, and controlled changes.
- **Upgrade and maintenance:** release/compatibility review, maintenance planning, backup, rollback preparation, and post-upgrade checks.
- **Remote troubleshooting:** remote access, layered fault isolation, log/counter review, route and neighbor checks, and service restoration.
- **Verification:** interface health, CPU/memory where applicable, routing adjacencies, VLAN forwarding, monitoring, and end-to-end reachability.

## Choosing a reference

- Start with the device folder README for source details, release, scope, sanitization, and limitations.
- Use [routing](../routing/) and [switching](../switching/) for technology-focused learning rather than vendor-specific device files.
- Source-derived references and independently authored labs are labelled separately.
- The exact hardware model is stated only when supported by the source material.

Check compatibility and dependencies on the exact platform and software release before adapting any configuration.
