# Cisco ASR 920

**Platform:** Cisco ASR 920-24SZ-M  
**Source software family:** IOS 15.6 / ASR920 universal image 03.18.02.SP2

This directory contains reduced, sanitized reference examples based on an ASR920 configuration export. The source design uses Ethernet service instances, bridge-domain interfaces, multiple VRFs, BGP per VRF, prefix-lists, route-maps, communities and QoS policing.

## Files

- [Base platform and management](./asr920-base-platform.cfg.example)
- [EVC and service-instance patterns](./asr920-evc-service-instances.cfg.example)
- [Bridge domains and BDI/VRF termination](./asr920-bridge-domain-vrf-bdi.cfg.example)
- [BGP global and VRF peering](./asr920-bgp-vrf-peering.cfg.example)
- [Prefix filters, communities and route-maps](./asr920-bgp-policy.cfg.example)
- [QoS policing patterns](./asr920-qos-policing.cfg.example)

## Technical areas represented

- ASR920-24SZ-M platform and IOS 15.6 software family
- VRF definitions and route distinguishers
- Ethernet service instances with 802.1Q encapsulation
- Symmetric single-tag pop and bridge-domain association
- Port-channel and TenGigabitEthernet service handoff patterns
- Bridge-domain interfaces for routed service termination
- Global BGP and IPv4 address-family per-VRF BGP
- Prefix-list filtering, route-maps and BGP communities
- Ingress/egress policy design and CIR policing
- Separate out-of-band management VRF, SSH and HTTP service hardening

## Sanitization

The original export contained live public and private IP addressing, peer addresses, autonomous system details, provider/customer labels, device identifiers, usernames, encrypted and type-7 passwords, an enable secret, and SNMP community information.

Those values have not been reproduced. The examples use documentation-only address ranges (RFC 5737), private example addressing, fictional ASNs, generic service labels and new example VLAN/BDI identifiers. No subscriber or provider inventory is included.

**Security action:** Treat every credential and SNMP community present in the original export as exposed. Rotate affected credentials and communities, review management access, and do not reuse the source secrets.

## Compatibility and validation

- The source identified an ASR-920-24SZ-M and IOS 15.6 / 03.18.02.SP2 software family.
- ASR920 feature support, EVC scale, BDI scale, QoS behavior, licensing and command syntax vary by PID, hardware revision and software release.
- These files are documentation examples, not a complete backup and not ready-to-paste production configuration.
- No Cisco parser, CML/EVE-NG image, physical ASR920 or live peer validation was performed.
- Review BGP import/export policy carefully. Prefix-lists and route-maps can unintentionally suppress or leak routes.
- Confirm port-channel member configuration, LACP mode, service-instance placement, bridge-domain behavior and QoS attachment points for the exact platform.

## Useful verification commands

```text
show version
show inventory
show license
show platform
show interfaces status
show etherchannel summary
show ethernet service instance
show bridge-domain
show ip interface brief
show vrf
show ip route vrf all
show ip bgp summary
show ip bgp vpnv4 all summary
show policy-map interface
show running-config
```

Use a maintenance window, configuration backup and reviewed rollback plan before making changes to a live router.
