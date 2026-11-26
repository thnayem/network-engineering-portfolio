# MikroTik RouterOS Configuration References

This directory contains three separate examples:

| File | Version | Purpose |
|---|---|---|
| [RouterOS 6.46.8 reference](./2023-06-17-routeros-v6-6.46.8-reference.rsc.example) | 6.46.8 | Reduced, anonymized example based on the uploaded RouterOS 6 configuration |
| [RouterOS 7 equivalent design](./2023-06-17-routeros-v7-equivalent-reference.rsc.example) | 7.x | Rewritten example showing the corresponding design using RouterOS 7 routing syntax |
| [RouterOS 7 VLAN/OSPF lab](./2026-03-18-routeros-v7-lab.rsc.example) | 7.x | Independent VLAN-aware bridge and OSPF lab |

## RouterOS 6 reference

The source export was dated 2023-06-17 and identified itself as RouterOS 6.46.8. The public file is deliberately reduced and anonymized. It demonstrates interface/VLAN layout, management bridging, addressing, DHCP, PCQ/simple queues, BGP, OSPF, NAT, firewall policy, and management-plane restrictions.

It is not a complete copy of the source export. Customer names, hostnames, leases, MAC addresses, public allocations, provider-specific route data, PPP credentials, VPN secrets, SMTP credentials, backup scripts, SNMP communities, and monitoring destinations were excluded.

## RouterOS 7 equivalent design

The RouterOS 7 file follows the same simplified lab topology and policy intent. It uses the RouterOS 7 BGP connection/filter-chain model and OSPF interface templates rather than the RouterOS 6 peer and network configuration model.

This is a design-level equivalent, not a line-by-line conversion of the full RouterOS 6 export. Some RouterOS 6 features and operational services were intentionally omitted rather than carried over without a safe, verified v7 mapping.

## Important validation boundary

Neither file has been imported into RouterOS or validated on a MikroTik device or CHR instance. The RouterOS 7 syntax and behavior must be checked against the exact target release. Do not import either file into a live router without reviewing every command, interface mapping, routing policy, firewall rule, and rollback plan.

All public examples use documentation-only address ranges and fictional identifiers. They are intended for technical review and lab practice, not direct deployment.
