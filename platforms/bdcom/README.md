# BDCOM Switch Configuration References

This folder contains two separate sanitized BDCOM running-configuration references supplied for portfolio documentation. The source exports represent different software builds and different port layouts; they are not combined into one device configuration.

## Devices

| Reference | Source software | Port layout evidenced by config | Main focus |
|---|---|---|---|
| [Access switch](./access-switch/) | 2.1.1B build 28530 | GigaEthernet0/1-0/28 | Access VLAN handoffs, per-port PVID/untagged VLAN, trunking, static port aggregation |
| [POP switch](./pop-switch/) | 2.2.0D build 78722 | GigaEthernet0/1-0/24 and TGigaEthernet0/1-0/4 | Subscriber/access VLAN handoffs, dual 10G uplinks, VLAN allow-lists, LLDP and RSTP |

The exact BDCOM hardware model is not identified in either supplied configuration, so no model number is assumed.

## Technical coverage

- RSTP mode and bridge priority
- VLAN database and VLAN interface management
- Access-style handoffs implemented with allowed VLAN, untagged VLAN and PVID
- 802.1Q trunk allow-lists
- Static port aggregation on the access-switch reference
- Primary/secondary 10G trunk uplinks on the POP reference
- Root guard and BPDU filter examples, retained as source-derived settings
- Management routing and SSH access patterns

## Sanitization

The original hostnames, site/customer/person labels, usernames and plaintext passwords, SNMP community, and management IP addresses have been removed or replaced. Management addresses use documentation-only ranges. VLAN IDs and port numbering are retained to preserve the source configuration's structure.

The public files are curated examples, not raw backups. They omit some nonessential lines and are not intended for direct import into a live switch.

## Validation boundary

The commands are based on the supplied BDCOM configuration syntax and have not been validated on physical hardware or an emulator. Verify command support on the exact BDCOM model and firmware. Review VLAN membership, uplink allow-lists, STP protections, aggregation behavior and management reachability before adapting. Use out-of-band access and a rollback plan for any live change.
