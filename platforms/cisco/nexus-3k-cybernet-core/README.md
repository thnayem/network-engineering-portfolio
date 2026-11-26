# Cisco Nexus 3000 Core Switch - NX-OS 7.0(3)I4(6)

## Source profile

- Platform: Cisco Nexus 3000 series
- Hardware profile in source: 48x10G + 4x40G
- NX-OS: 7.0(3)I4(6)
- Source configuration timestamp: 18 June 2024
- Source hostname and operational labels: anonymized
- Source-derived configuration is reduced and sanitized

The supplied configuration identifies the Nexus 3000 family and port profile, but does not provide an explicit PID. No exact model is inferred.

## Files

- `nexus-3k-source-derived-mst-reference.cfg.example`: representative source-derived MST, VLAN, LACP, trunk and interface configuration. BPDU filtering has been removed from the general-purpose uplink examples because it suppresses BPDUs and can undermine loop protection.
- `nexus-3k-stp-rstp-bpdu-design.cfg.example`: separately labelled design template showing a conservative Rapid-PVST+ edge/access policy, BPDU Guard, Root Guard and Loop Guard. It is a design alternative, not a claim about the original production configuration.

## STP/RSTP design decisions

The source ran MST (`spanning-tree mode mst`) and set MST instance 0 priority to 0. That source behaviour is retained in the MST reference. The source also applied `spanning-tree bpdufilter enable` on several provider/transport-facing trunks and port-channels. BPDU Filter suppresses BPDU transmission/reception on the configured interface and is not interchangeable with BPDU Guard. It should not be copied blindly to redundant switch links.

The separate RSTP template uses Rapid-PVST+ for per-VLAN rapid spanning tree. Apply it only where the design requires Rapid-PVST+ and the neighbouring switches support a compatible spanning-tree mode. For a multi-vendor MST domain, retain MST and configure identical region name, revision and VLAN-to-instance mapping on all intended region members.

### Recommended control placement

- **BPDU Guard:** edge/host-facing access ports only, normally together with PortFast.
- **Root Guard:** designated downstream-facing switch ports where this device must remain the root; never apply to the intended root's upstream path.
- **Loop Guard:** suitable non-designated switch-facing ports where unidirectional link failure is a concern; validate platform support and topology.
- **BPDU Filter:** avoid on switch-to-switch links. Use only for a narrowly justified edge case with explicit loop-prevention controls.
- **Port-channel:** configure STP policy on the logical port-channel where supported; avoid inconsistent member-level policy.
- **Root bridge:** define root placement intentionally. The source MST reference preserves priority 0; do not make a second switch root without a planned hierarchy.

## Validation before deployment

Check `show spanning-tree summary`, `show spanning-tree mst`, `show spanning-tree vlan <id>`, `show port-channel summary`, `show lacp neighbor`, `show interface trunk`, and `show logging logfile`. Confirm VLAN mapping, MST region parameters, root bridge, blocked/forwarding ports, BPDU counters, LACP state, and failover behaviour during a maintenance window. Do not paste either example into production unchanged.

## Sanitization

Usernames, password hashes, SNMPv3 localized keys, SNMP community, management IPs, original hostname, provider/customer/site names, server labels and operational descriptions have been removed or replaced. VLAN IDs have been remapped to documentation values. The CoPP policy is represented only as a feature note; platform-default ACL internals and security credentials are not published.
