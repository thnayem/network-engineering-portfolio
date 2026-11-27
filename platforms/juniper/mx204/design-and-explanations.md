# Juniper MX204: Design and Configuration Notes

## 1. Scope

This document explains the separate Juniper MX204 network engineering demonstration. It covers the design patterns and configuration areas represented by the MX204 examples. The MX204 and MX240 materials are maintained independently.

## 2. Public configuration

The [MX204 demo](./mx204-demo.set.example) is a sanitized representative configuration for technical review. It is not a raw device backup and must not be treated as a paste-and-deploy configuration.

## 3. Architecture and technical areas

The MX204 documentation and associated labs cover:
- Logical systems and routing-instance separation
- Logical-tunnel connectivity between routing contexts
- Aggregated Ethernet and VLAN-tagged routed interfaces
- BGP sessions and peer policy
- Import/export policy and prefix filtering
- Static routing and service-specific forwarding
- Firewall filters and filter-based forwarding patterns
- Service bandwidth policing

Refer to the individual lab files for their exact scope, dependencies, and configuration details.

## 4. Keep MX204 and MX240 separate

The MX240 examples are maintained under [../mx240](../mx240/). Do not infer MX240 hardware details from this MX204 material or combine the two platform configurations.

## 5. Sanitization

Public references use documentation prefixes and private lab values in place of operational addresses, peer IPs, loopbacks, service prefixes, ASNs, account names, and network identifiers. No real customer/provider identities, credentials, authentication secrets, SNMP communities, or API keys are included.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
