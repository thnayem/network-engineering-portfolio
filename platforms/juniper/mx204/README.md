# Juniper MX204 Examples

This directory contains Juniper MX204 configuration references and smaller labs. The MX204 material is kept separate from the MX240 example because the hardware and configuration scope differ.

## Files and labs

- [MX204 set-format example](./mx204-demo.set.example)
- [Design notes](./design-and-explanations.md)
- [Verification and rollback](./verification-and-rollback.md)
- [Logical systems lab](./logical-systems/)
- [Firewall filter lab](./firewall-filters/)
- [BGP policy lab](../../../routing/bgp-policy/)
- [Policy-Based Routing lab](../../../routing/pbr/)

## Topics covered

The examples cover logical systems, logical tunnels, aggregated Ethernet, VLAN-tagged routed interfaces, BGP policy, static routes, firewall filters, filter-based forwarding, and service policing.

## Scope and validation

The files are shortened examples, not original device backups or complete deployment configurations. Some labs are independent exercises rather than a reproduction of a single implementation. Check each file's dependencies and intended scope before using it.

No MX204 commit-check or device validation has been performed for this public set. Verify syntax and feature support against the target Junos release and hardware, then test in an isolated lab.
