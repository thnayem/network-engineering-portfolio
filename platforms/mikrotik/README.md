# MikroTik RouterOS Configuration References

This directory contains RouterOS 6 and RouterOS 7 references based on selected concepts from multiple dated exports and separate lab examples. The public examples are rewritten, curated, and reduced; they do not reproduce original live configurations.

## Main configuration references

| File | Version | Purpose |
|---|---|---|
| [CCR1009 edge/BGP reference](./2023-04-22-ccr1009-routeros-v6-6.47-edge-bgp-reference.rsc.example) | 6.47 | Curated VLAN handoffs, EoIP/GRE, IPv4/IPv6 BGP peers, route filters, NAT and service settings. Based on a 2023-04-22 export. |
| [RouterOS 6.46.8 reference](./2023-06-17-routeros-v6-6.46.8-reference.rsc.example) | 6.46.8 | Reduced main configuration example |
| [RouterOS 7 equivalent design](./2023-06-17-routeros-v7-equivalent-reference.rsc.example) | 7.x | Rewritten design equivalent using RouterOS 7 routing syntax |
| [RouterOS 7 VLAN/OSPF lab](./2026-03-18-routeros-v7-lab.rsc.example) | 7.x | Separate VLAN-aware bridge and OSPF lab |
| [CRS309 switching reference](./crs309/) | 6.48.2 | Canonical CRS309-1G-8S+ VLAN-aware bridge, tagged trunks, and bridge VLAN membership |

The older top-level file [CRS309 reference](./crs309-1g-8s-plus-routeros-6.48.2-vlan-switch-reference.rsc.example) is retained for provenance only. Use the canonical file under `crs309/` for current review; the two references are not guaranteed to be byte-identical.

## Routing and policy segments

### RouterOS 6

- [IPv4 and IPv6 BGP, prefix filters and next-hop policy](./segments/routeros-v6-bgp-ipv4-ipv6.rsc.example)
- [OSPF input filtering, static routes and policy-routing example](./segments/routeros-v6-ospf-route-policy.rsc.example)
- [Firewall address lists, NAT, and mangle/PBR](./segments/routeros-v6-firewall-nat-pbr.rsc.example)
- [PCQ and subscriber-tier queue examples](./segments/routeros-v6-qos-pcq.rsc.example)

### RouterOS 7

- [Dual-stack BGP connections and routing filters](./segments/routeros-v7-bgp-ipv4-ipv6.rsc.example)
- [OSPF instances, areas, interface templates and policy routing](./segments/routeros-v7-ospf-route-policy.rsc.example)
- [Firewall address lists, NAT, and mangle/PBR](./segments/routeros-v7-firewall-nat-pbr.rsc.example)
- [PCQ and subscriber-tier queue examples](./segments/routeros-v7-qos-pcq.rsc.example)

## What this CCR1009 reference covers

The 2023-04-22 RouterOS 6.47 source was a CCR1009-8G-1S-1S+ export. This curated reference retains representative interface/VLAN handoffs, EoIP and GRE tunnels, multiple BGP instances and peers, IPv4/IPv6 addressing, static route/failover patterns, prefix filtering, NAT, PCQ, and selected management settings. It is a selected technical excerpt, not a complete backup.

Peer/provider names, site labels, public allocations, internal addressing, ASNs, MAC addresses, serial/software identifiers, SNMP community, mailbox details, and user identifiers have been anonymized or replaced. Address values are RFC1918 lab placeholders. Because the addressing and identifiers are changed, this file is not directly importable and is not a faithful working topology.

## What was retained from the earlier RouterOS 6.46.8 export

The earlier export includes VLAN handoffs for multiple upstream/service networks, IPv4 and IPv6 BGP peers, separate import/export filters, IPv6 next-hop handling, OSPF input filtering, static routes to access networks, route rules, address lists for public/internal/NAT-bypass and application groups, source/destination NAT and netmap, mangle-based policy routing, PCQ queue types, and per-subscriber/simple-queue tiers.

The public segments preserve these technical patterns with fictional names, documentation-only prefixes, and lab ASNs. They do not retain original peer addresses, public allocations, AS numbers, provider/service labels, customer names, subscriber targets, MAC addresses, PPP accounts, passwords, IPsec secrets, email settings, remote logging destinations, SNMP community, scripts, or scheduler jobs.

## RouterOS 6 and 7 are not syntax-identical

RouterOS 7 uses the BGP connection/template/session model and script-style routing filters. OSPF uses instances, areas, and interface templates. Policy routing also requires explicit routing-table configuration in v7. The v7 files are design equivalents, not a line-by-line conversion.

The BGP v7 example uses the explicit BGP instance menu available in RouterOS 7.20 and later. For earlier v7 releases, review the instance behavior and syntax against that release.

## Validation boundary

These files have not been imported into RouterOS or validated on a MikroTik device/CHR. Some examples are independent lab segments and require the referenced interfaces, addresses, peers, and routing tables to exist. Review command support and syntax against the exact RouterOS release. Test in an isolated CHR or lab, confirm route advertisements and NAT counters, and prepare a rollback before any live use.

The CCR1009 file is a curated, anonymized excerpt and must not be imported as-is. No example is intended for direct deployment.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
