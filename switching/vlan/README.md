# VLAN Segmentation

**Lab date:** 2026-03-18 (reference archive date; independently authored example)

| VLAN | Name | Example subnet |
|---:|---|---|
| 10 | USERS | 192.0.2.0/24 |
| 20 | VOICE | 198.51.100.0/24 |
| 99 | MANAGEMENT | 203.0.113.0/24 |

These are documentation-only TEST-NET ranges.

## Design notes
- Use access mode for endpoint-facing ports.
- Use 802.1Q trunks between switches and to L3 gateways.
- Allow only required VLANs on each trunk.
- Keep management access restricted.
- Define the native VLAN deliberately and consistently.

See vendor-specific examples in [Cisco](../../platforms/cisco/) and [Huawei](../../platforms/huawei/).
