# BDCOM POP Switch Reference

Source software: 2.2.0D build 78722. Exact hardware model is not stated in the source export.

The reference documents a 24-port Gigabit Ethernet plus four 10-Gigabit Ethernet interface layout, RSTP priority 4096, per-port VLAN handoffs, dual 10G uplink trunks with extensive VLAN allow-lists, LLDP, root guard and a source-configured BPDU filter on one customer-facing trunk.

Management addressing is replaced with documentation-only prefixes. Hostname, human/site labels, credentials and SNMP community are removed. The example is curated and has not been validated on hardware.

See [sanitized configuration](./bdcom-pop-switch-reference.cfg.example).