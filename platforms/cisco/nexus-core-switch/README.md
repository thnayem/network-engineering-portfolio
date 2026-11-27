# Cisco Nexus Core Switch - Source-Derived Reference

## Source identification

- Platform family: Cisco Nexus / NX-OS
- Source NX-OS release: 7.0(3)I4(3)
- Source configuration timestamp: 28 April 2023
- Hardware model: not stated in the supplied configuration; intentionally not inferred
- Source type: running configuration supplied for portfolio documentation

This is a sanitized, reduced reference derived from a supplied running configuration. It is not a raw backup and is not a complete device configuration. It preserves representative design patterns while replacing organization, provider, customer, server, port-description, VLAN-purpose, management-address, credential, and monitoring identifiers.

## Preserved technical areas

- MST spanning tree and MST region/instance structure
- VLAN database and service segmentation
- SVI-based management interface
- LACP active port-channels
- Trunk allow-lists and per-port VLAN handoffs
- 10-Gigabit and 1-Gigabit uplink examples
- Source BPDU filtering was observed on selected uplinks but has been omitted from the public command template because it can undermine spanning-tree loop protection
- SPAN source/destination monitoring session
- NX-OS control-plane policy framework (documented, not copied wholesale)

## Sanitization notes

- All usernames, password hashes, SNMPv3 localized keys, and SNMP communities have been removed.
- Real hostname, VDC name, provider/customer names, server names, port descriptions, and management IPs have been replaced.
- VLAN IDs have been remapped to documentation values and names generalized.
- Source model was not provided, so no Nexus PID is claimed.
- Source configuration includes a large set of default CoPP ACLs and class maps. The public example documents the CoPP feature rather than reproducing platform-default policy internals.

## Important implementation note

The source uses `channel-group ... mode active` on selected member interfaces, so the examples retain LACP active mode. This is separate from the static EtherChannel behavior in the Cisco 7606-S reference.

## Validation

The sanitized file is a documentation reference and has not been loaded into a physical Nexus switch or checked by a Cisco configuration parser. Validate NX-OS feature support, interface naming, VLAN membership, MST region consistency, LACP partner settings, SPAN resource limits, and management reachability against the exact hardware and release before lab use. Do not reintroduce BPDU Filter on switch-to-switch links without a documented exception and compensating loop-prevention controls. Do not paste it into production unchanged.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
