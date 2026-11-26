# Portfolio Structure and Navigation

This guide explains how the repository is organized and where new material belongs. The structure intentionally separates vendor/device references from protocol and technology examples.

## Navigation model

```text
network-engineering-portfolio/
|
|-- platforms/                 Vendor and device-family references
|   |-- arista/
|   |-- bdcom/
|   |-- cisco/
|   |   |-- asr920/
|   |   |-- 7606s/
|   |   |-- nexus-core-switch/
|   |   \-- nexus-3k-cybernet-core/
|   |-- huawei/
|   |-- juniper/
|   |   |-- mx204/
|   |   \-- mx240/
|   \-- mikrotik/
|       |-- crs309/
|       \-- segments/
|
|-- routing/                   Protocol and routing-policy topics
|   |-- bgp/
|   |-- bgp-policy/
|   |-- ospf/
|   |-- pbr/
|   |-- policy/
|   \-- static-routing/
|
|-- switching/                 Layer 2 and switching topics
|   |-- acl/
|   |-- nexus/
|   |-- rstp/
|   \-- vlan/
|
|-- network-architecture/      Logical design and segmentation
|-- gpon-olt/                  Vendor-neutral GPON operations
|-- troubleshooting/           Operational runbooks
|-- reference-dates/           Archive provenance notes
|-- .github/workflows/         Repository automation
|-- README.md                  Portfolio landing page
|-- SECURITY.md                Public-data and disclosure rules
\-- PRODUCTION-IMPLEMENTATIONS.md
```

## Placement rules

### 1. Vendor and device-specific material
Place a configuration reference under `platforms/<vendor>/<device-family>/`. Keep different device families, software releases, and source dates separate when they represent different source configurations.

Examples:
- Cisco ASR 920: `platforms/cisco/asr920/`
- Juniper MX204: `platforms/juniper/mx204/`
- MikroTik CRS309: `platforms/mikrotik/crs309/`

Do not place Juniper MX device files under Cisco, Nexus, or generic switching directories.

### 2. Protocol and technology material
Place reusable protocol examples under the relevant technical domain, independent of vendor where practical.

Examples:
- BGP policy: `routing/bgp-policy/`
- OSPF: `routing/ospf/`
- PBR: `routing/pbr/`
- VLAN/trunk concepts: `switching/vlan/`
- RSTP concepts: `switching/rstp/`

A vendor-specific file may be linked from a domain README, but its canonical copy should remain in the vendor/device directory. Avoid maintaining duplicate copies.

### 3. Keep distinct source references distinct
Two source-derived configurations must not be merged merely because they use the same vendor or product family. Preserve known differences in model family, software release, configuration date, interface layout, and source scope. If the exact hardware model is unknown, state that instead of inferring it.

### 4. Standard device-folder contents
Where useful, a device folder should contain:

- `README.md` - source, platform/release, scope, sanitization, limitations, and links
- `*.cfg.example`, `*.rsc.example`, or `*.set.example` - sanitized configuration reference
- `design-and-explanations.md` - design intent and trade-offs
- `topology-and-packet-flow.md` - logical flow, when it adds value
- `verification-and-rollback.md` - validation and safe-change notes
- `segments/` - independently useful, clearly scoped feature examples

Do not create empty folders just to anticipate future content. Add a directory when there is a real example or a useful README explaining its planned scope.

## File naming

Use lowercase kebab-case names and include the platform/software release when it materially helps identify compatibility.

Preferred patterns:
- `<device>-<release>-<topic>.cfg.example`
- `<platform>-routeros-v7-<topic>.rsc.example`
- `<device>-<topic>.set.example`

Use `.example` suffixes for all configuration examples so they are not mistaken for raw backups or import-ready files.

## Documentation and validation checklist

Before publishing a new item:

1. Identify whether it is source-derived, independently authored, or a design note.
2. Record the exact platform and software release when known.
3. Remove credentials, hashes, SNMP communities, keys, serials, real IP allocations, hostnames, descriptions, and customer/provider identifiers.
4. Check the entire diff and search the repository history for sensitive data.
5. Confirm links and relative paths.
6. Document feature dependencies, incomplete sections, and compatibility limits.
7. Add verification commands and rollback considerations where appropriate.
8. Never claim parser, emulator, or hardware validation unless it was actually performed.

See [SECURITY.md](./SECURITY.md) for publication restrictions and [PRODUCTION-IMPLEMENTATIONS.md](./PRODUCTION-IMPLEMENTATIONS.md) for how source-derived references are described.
