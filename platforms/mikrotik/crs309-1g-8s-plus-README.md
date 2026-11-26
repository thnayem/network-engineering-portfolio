# MikroTik CRS309-1G-8S+ VLAN Switching Reference

- **Hardware:** MikroTik CRS309-1G-8S+
- **RouterOS:** 6.48.2
- **Source:** Sanitized, source-derived reference from a device export. The source export clock was unreliable, so no backup date is assigned.
- **Scope:** VLAN-aware bridge, eight SFP+ switch ports, tagged VLAN membership, management VLAN interfaces, SNMP, neighbor-discovery restriction and RoMON.

## Technical coverage

- VLAN filtering enabled on the bridge.
- Bridge ports accept tagged frames only and use ingress filtering.
- Explicit per-VLAN tagged-port membership, including VLAN ranges.
- Separate management VLAN interfaces and documentation-only management addressing.
- Port-specific link settings and selected disabled interfaces retained as source-derived behavior.

## Sanitization

Site, provider, customer and service labels were replaced with generic names. Management addresses use RFC 5737 documentation ranges. Device serial/software identifiers, the original SNMP community name, mailbox details, scheduled email-backup scripts and custom management service ports were not published. VLAN IDs and tagged-port relationships are retained as representative technical configuration.

## Important notes

This is not a raw backup and is not intended for direct import. The management addresses and labels are placeholders. Review the original topology, VLAN membership, bridge hardware-offload behavior, management access, and exact RouterOS release before adapting it. The source had connection tracking disabled and an enabled SNMP/RoMON configuration; these are retained as source-derived settings, not general recommendations.

No RouterOS import or hardware validation has been performed on this public example.
