# Huawei MA5800-X7 GPON OLT

**Platform:** Huawei MA5800-X7  
**Source software label:** MA5800V100R018:5600  
**Configuration family:** GPON, ONT profiles, GEM mapping, service VLANs, uplinks and management plane

This directory contains a sanitized reference derived from a MA5800-X7 configuration export. The public example demonstrates the structure and operating concepts of a GPON OLT configuration without publishing the original subscriber inventory or management secrets.

## Configuration example

- [MA5800-X7 V100R018 sanitized reference](./ma5800-x7-v100r018-gpon-reference.cfg.example)

## What the source configuration demonstrated

- Chassis board inventory, including a GPON service board
- DBA profiles with assured and maximum bandwidth parameters
- ONT service profiles with transparent Ethernet UNI VLAN handling
- ONT line profiles, T-CONTs, GEM ports and VLAN mappings
- Multiple service VLANs and uplink VLAN membership
- 10GE uplink port speed/auto-negotiation settings
- GPON port ONT auto-discovery
- ONT registration using serial-number authentication and OMCI
- Service-port bindings between VLANs, GPON ONTs and GEM ports
- ONT Ethernet native-VLAN assignment
- In-band VLAN interface and out-of-band MEth0 management addressing
- Static default routing, AAA, SSH and SNMP management configuration

## Privacy treatment

The original export contained local account password hashes, FTP credentials, SNMP community strings, ONT serial numbers, subscriber descriptions, a large live service-port inventory, management IP addresses and device-specific identifiers. Those values and records are not included in the public example.

The example uses documentation-only addresses and a clearly marked ONT serial placeholder. It does not reproduce customer names, live ONT registrations, the original service-port table, encrypted credentials or SNMP communities.

## Important limitations

- This is a reduced reference, not a complete backup or a ready-to-import configuration.
- The source export identified MA5800 V100R018 build 5600. Syntax and feature availability can vary by patch, board type, license and chassis configuration.
- Board/slot numbering, uplink ports, VLAN membership, DBA values, ONT model capabilities and service profiles must be checked against the target OLT.
- The example ONT registration and service-port commands are templates. Replace placeholders only with authorized device/subscriber data.
- No MA5800 emulator, live OLT or Huawei command parser validation was performed for this publication.

## Verification commands

```text
display version
display board 0
display vlan all
display port vlan
display ont info 0 all
display ont autofind all
display service-port all
display dba-profile all
display ont-lineprofile gpon all
display ont-srvprofile gpon all
display interface mpu 0/8
display interface gpon 0/7
display ip routing-table
```

Use a maintenance window and a reviewed rollback plan before making changes on a live OLT.
