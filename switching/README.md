# Switching

**Production operations:** Hands-on remote configuration, maintenance, upgrades, and troubleshooting of live production switching infrastructure, including VLANs, access/trunk ports, STP, EtherChannel/LACP, interface health, and service restoration.

- [VLAN segmentation](./vlan/)
- [RSTP and loop prevention](./rstp/)
- [ACL concepts](./acl/)
- [Cisco Nexus notes](./nexus/)
- [Cisco Nexus core switch (NX-OS 7.0(3)I4(3))](../platforms/cisco/nexus-core-switch/)

## Vendor-specific switching examples

- [MikroTik CRS309 RouterOS 6.48.2](../platforms/mikrotik/crs309/) - VLAN-aware bridge and tagged trunk configuration

## Operational workflow

- Review current port state, VLAN membership, trunk allow-lists, STP topology, and interface counters.
- Plan remote changes with an alternate management path and rollback where possible.
- Verify link state, MAC learning, VLAN forwarding, loop protection, LACP state, and end-to-end connectivity after changes.

All examples are fictional, independently authored lab material. See vendor folders for syntax-specific samples. Production experience is distinct from the validation status of these published examples.
