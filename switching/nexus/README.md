# Cisco Nexus 3000 Series (NX-OS) Portfolio

This directory contains independently authored Nexus 3K-style lab examples. They use fictional labels and documentation-only addressing. They are not raw device backups and do not identify an employer or network.

## Source-derived core switch reference

A separate source-derived NX-OS 7.0(3)I4(3) configuration is documented under [Cisco Nexus core switch](../../platforms/cisco/nexus-core-switch/). That reference is based on a supplied running configuration and is distinct from the generic lab examples below.

## Configuration examples

| Topic | File |
|---|---|
| VLAN, access ports and trunk | [nexus3k-vlan-access-trunk.cfg.example](./nexus3k-vlan-access-trunk.cfg.example) |
| LACP EtherChannel / port-channel | [nexus3k-lacp-port-channel.cfg.example](./nexus3k-lacp-port-channel.cfg.example) |
| STP root, edge, BPDU Guard and Root Guard | [nexus3k-spanning-tree-protection.cfg.example](./nexus3k-spanning-tree-protection.cfg.example) |
| Layer 3 SVI and OSPF | [nexus3k-layer3-svi-ospf.cfg.example](./nexus3k-layer3-svi-ospf.cfg.example) |
| eBGP underlay and outbound route-map | [nexus3k-bgp-underlay.cfg.example](./nexus3k-bgp-underlay.cfg.example) |
| Basic VLAN and trunk lab | [nexus-vlan-trunk-lab.cfg.example](./nexus-vlan-trunk-lab.cfg.example) |

## Technical scope

The examples cover VLAN segmentation, access/trunk interfaces, allowed VLAN lists, LACP active port-channel, Rapid-PVST concepts, STP edge/network port types, BPDU Guard, Root Guard, Layer 3 SVI gateways, routed physical interfaces, OSPF adjacency, eBGP peering, prefix-lists, and route-map based outbound filtering.

## Platform compatibility and validation

Nexus 3000 hardware families and NX-OS releases do not all support identical feature sets or syntax. In particular, Layer 3 routing, OSPF, BGP, STP modes, LACP behavior, and interface capabilities must be checked against the exact switch PID and NX-OS release.

These files have not been imported into a Nexus 3K device, NX-OSv, or a vendor parser in this task. Treat them as technical lab references, not validated production configurations. Before use, check feature support, interface naming, transceiver/speed capabilities, MTU, VLAN consistency, routing adjacencies, and rollback access.

## Suggested verification commands

```text
show version
show module
show feature
show vlan brief
show interface trunk
show port-channel summary
show lacp neighbor
show spanning-tree summary
show spanning-tree inconsistentports
show ip interface brief
show ip ospf neighbors
show ip route
show bgp ipv4 unicast summary
show running-config
```

Use only commands supported by the target NX-OS release. No production addresses, organization names, credentials, customer information, or private topology details are included.
