# Platform Index

Vendor-specific references are grouped here. Keep device families and source releases separate when they represent distinct configurations.

| Vendor | Device/reference | Scope |
|---|---|---|
| [Cisco](./cisco/) | [ASR 920](./cisco/asr920/), [7606-S](./cisco/7606s/), [Nexus core switch](./cisco/nexus-core-switch/), [Nexus 3000 core](./cisco/nexus-3k-cybernet-core/) | IOS/IOS XE, NX-OS, EVC, VRF, BGP, switching |
| [Arista](./arista/) | [DCS-7050S-52](./arista/dcs-7050s-52/) | EOS, VLANs, MSTP, LACP |
| [Juniper](./juniper/) | [MX204](./juniper/mx204/), [MX240](./juniper/mx240/) | Junos, logical systems, routing policy, filters |
| [MikroTik](./mikrotik/) | [CCR references](./mikrotik/), [CRS309](./mikrotik/crs309/) | RouterOS 6/7, BGP, OSPF, PBR, NAT, QoS, VLAN bridge |
| [BDCOM](./bdcom/) | [Access switch](./bdcom/access-switch/), [POP switch](./bdcom/pop-switch/) | VLAN handoffs, trunks, RSTP, aggregation |
| [Huawei](./huawei/) | [MA5800-X7](./huawei/) | GPON, DBA, ONT profiles, GEM mapping, service VLANs |

## Choosing a reference

- Start with the device folder README for source details, release, scope, sanitization, and limitations.
- Use [routing](../routing/) and [switching](../switching/) for technology-focused learning rather than vendor-specific device files.
- Source-derived references and independently authored labs are labelled separately.
- The exact hardware model is stated only when supported by the source material.

All configurations are examples for review and lab adaptation. Check compatibility and dependencies on the exact platform and software release before use.
