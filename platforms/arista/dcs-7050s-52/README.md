# Arista DCS-7050S-52 Core Switch

**Platform:** Arista DCS-7050S-52  
**EOS release:** 4.18.11M

This reference is derived from a supplied running configuration. It retains the source topology patterns and interface/VLAN relationships while removing organization-specific identifiers and management secrets.

## Configuration

- [Sanitized DCS-7050S-52 running-config reference](./dcs-7050s-52-eos-4.18.11m-reference.cfg.example)

## Technical coverage

- EOS 4.18.11M platform baseline
- MSTP mode and MST region configuration
- VLAN database and service VLAN naming
- 802.1Q trunk interfaces and allowed VLAN lists
- LACP port-channels (Port-Channel2 and Port-Channel3)
- Link aggregation member interfaces
- BPDU Guard edge-port example; source BPDU Filter settings are documented but commented out in the public configuration because they can suppress loop-detection BPDUs
- Port security on a fiber-facing trunk
- 1G forced-speed and auto-speed interface patterns
- Management SVI, default route and SSH management source interface
- Layer 3 routing enabled on the switch

## Sanitization

Removed or replaced:
- Original hostname and local domain
- Organization, customer, provider and peer names in interface descriptions
- Local usernames and all SHA-512 password hashes
- SNMP community string
- Original management IP address and default gateway

The published example uses generic interface descriptions, a reserved documentation domain, and RFC 5737 documentation addressing. No original account credentials or SNMP community are included.

**Credential response:** The source configuration exposed password hashes and an SNMP community. Treat these as compromised: rotate all affected account passwords, replace the SNMP community, and review access logs. Do not reuse the original hashes or community string.

## Review points before lab or production use

The following behaviors were present in the source and are preserved or explicitly documented rather than silently changed:

1. **STP disabled for VLAN 1375 and 2375.** This can remove loop protection for those VLANs. Confirm the Layer-2 topology and loop-prevention design before enabling or disabling STP.
2. **BPDU Filter on multiple uplinks.** The source used BPDU filtering on multiple uplinks; those commands are commented out in the public example. BPDU filtering can hide spanning-tree information and increase loop risk. Do not enable it on switch-to-switch links without a documented exception and compensating controls.
3. **BPDU Guard on a trunk interface.** Confirm the connected device is an edge device and that receiving a BPDU should err-disable/protect the port.
4. **Broad trunk VLAN ranges.** Ethernet8 permits a very wide VLAN range; Ethernet10 and several other ports have no explicit allowed-VLAN list. Restrict trunks to only the VLANs required by each link.
5. **Port security on a trunk.** Confirm the feature's behavior and suitability on the exact EOS release and interface role.
6. **VLAN references not present in the explicit VLAN list.** The source interface allowed lists include VLAN IDs such as 103, 120, 203, 4087 and 4089 that are not all explicitly declared in the shown VLAN database. Confirm VLAN creation and propagation.
7. **MST region consistency.** Region name, revision and VLAN-to-instance mapping must match across the intended MST region. The supplied source did not include an MST instance-to-VLAN mapping.

## Verification commands

```text
show version
show inventory
show vlan
show interfaces status
show interfaces trunk
show port-channel summary
show lacp neighbor
show spanning-tree
show spanning-tree mst configuration
show mac address-table
show ip interface brief
show ip route
show management ssh
show running-config
```

No EOS parser or physical DCS-7050S-52 validation was performed. Check command support and feature behavior against EOS 4.18.11M and the exact switch hardware before adapting this reference.
