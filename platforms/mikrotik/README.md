# MikroTik RouterOS Configuration References

This directory contains RouterOS 6 and RouterOS 7 references based on selected concepts from an uploaded RouterOS 6.46.8 export dated 2023-06-17. The original export is 1,200 lines. The public examples are rewritten and reduced; they do not reproduce the original live configuration.

## Main configuration references

| File | Version | Purpose |
|---|---|---|
| [RouterOS 6.46.8 reference](./2023-06-17-routeros-v6-6.46.8-reference.rsc.example) | 6.46.8 | Reduced main configuration example |
| [RouterOS 7 equivalent design](./2023-06-17-routeros-v7-equivalent-reference.rsc.example) | 7.x | Rewritten design equivalent using RouterOS 7 routing syntax |
| [RouterOS 7 VLAN/OSPF lab](./2026-03-18-routeros-v7-lab.rsc.example) | 7.x | Separate VLAN-aware bridge and OSPF lab |

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

## What was retained from the source concepts

The uploaded export includes VLAN handoffs for multiple upstream/service networks, IPv4 and IPv6 BGP peers, separate import/export filters, IPv6 next-hop handling, OSPF input filtering, static routes to access networks, route rules, address lists for public/internal/NAT-bypass and application groups, source/destination NAT and netmap, mangle-based policy routing, PCQ queue types, and per-subscriber/simple-queue tiers.

The public segments preserve these technical patterns with fictional names, documentation-only prefixes, and lab ASNs. They do not retain the original peer addresses, public allocations, AS number, provider/service labels, customer names, subscriber targets, MAC addresses, PPP accounts, passwords, IPsec secrets, email settings, remote logging destinations, SNMP community, scripts, or scheduler jobs.

## RouterOS 6 and 7 are not syntax-identical

RouterOS 7 uses the BGP connection/template/session model and script-style routing filters. OSPF uses instances, areas, and interface templates. Policy routing also requires explicit routing-table configuration in v7. The v7 files are design equivalents, not a line-by-line conversion.

The BGP v7 example uses the explicit BGP instance menu available in RouterOS 7.20 and later. For earlier v7 releases, review the instance behavior and syntax against that release.

## Validation boundary

These files have not been imported into RouterOS or validated on a MikroTik device/CHR. Some examples are independent lab segments and require the referenced interfaces, addresses, peers, and routing tables to exist. Review command support and syntax against the exact RouterOS release. Test in an isolated CHR or lab, confirm route advertisements and NAT counters, and prepare a rollback before any live use.

All addresses are documentation/private lab values. No example is intended for direct deployment.
