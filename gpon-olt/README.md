# GPON OLT and ONU Operations

## Scope

This section provides a vendor-neutral operational checklist for GPON access networks. It intentionally contains no real OLT export, subscriber identity, ONU serial number, service profile, VLAN allocation, or provider-specific topology.

## Basic troubleshooting sequence

1. Confirm OLT chassis, control board, PON port, and uplink status.
2. Check whether the ONU is discovered, registered, and online.
3. Review optical receive/transmit levels against the vendor's supported range.
4. Check fiber path, connector cleanliness, splitter path, patch panel, and bend radius.
5. Confirm the ONU service profile, line profile, service profile, and VLAN mapping.
6. Verify uplink VLAN tagging and upstream reachability.
7. Check alarms, LOS/LOF events, dying-gasp events, and recent flap history.
8. Record timestamps and test results without exporting subscriber credentials or personal data.

## Safe evidence collection

- Use fictional ONU labels in screenshots and documentation.
- Mask serial numbers, MAC addresses, customer names, phone numbers, and service IDs.
- Do not publish full OLT backups or subscriber database exports.
- Share optical measurements only after removing subscriber and location identifiers.

## Change control

Before changing PON profiles or VLAN mapping, identify affected services, save an approved backup in a private location, confirm rollback steps, and arrange an appropriate maintenance window.

Vendor command syntax and optical thresholds vary by platform. Use the official manual for the exact OLT model and software release.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
