# MikroTik CRS309 Switching Reference

## Platform and source

- Hardware: MikroTik CRS309-1G-8S+
- Source RouterOS release: 6.48.2
- Configuration type: curated, anonymized Layer 2 switching reference
- Source export date: not relied on; the source device clock was not a trustworthy backup timestamp

This reference is based on a CRS309 export supplied for portfolio documentation. It is the canonical location for the current public example; the older top-level CRS309 reference is retained separately for provenance. It preserves representative bridge VLAN filtering, tagged-only bridge ports, VLAN membership, trunk roles, and management-plane examples while removing site, provider, customer, serial, software ID, user, email, and other identifying values.

## Switching design represented

- VLAN-aware bridge with `vlan-filtering=yes`
- Tagged-only ingress on bridge member ports
- Ingress filtering enabled on bridge ports
- Explicit bridge VLAN membership for multiple VLANs and VLAN ranges
- Trunk links with selected VLAN allow-lists
- Management VLAN interfaces and a default management route
- RouterOS 6.48.2 syntax

## Important source-specific details

The source uses a CRS309-1G-8S+ with eight SFP+ ports. The curated export retains the source's bridge/VLAN architecture and representative port membership, but uses generic interface comments and renamed port aliases where needed. The original service/provider labels and site-specific IP addresses are not published.

This is not a RouterOS 7 conversion. RouterOS 7 equivalents should be maintained as a separately labelled variant and validated against the target release.

## Management-plane defaults

SNMP and RoMON commands are intentionally omitted from the public example. Connection tracking is left at the platform default rather than disabled. If management monitoring is needed in an authorized lab, configure SNMPv3 with unique credentials and restrict access to a management network.

## Validation and safety

The example has not been imported into a CRS309 or validated against live hardware. Review VLAN membership, bridge CPU-port behavior, management reachability, and port roles before adapting it. Apply changes through a controlled maintenance window with out-of-band access and a rollback plan. Do not paste this file into production unchanged.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
