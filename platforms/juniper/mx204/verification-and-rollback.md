# MX204 Lab: Verification, Commit Safety, and Rollback

## Before loading

1. Confirm the exact MX204 hardware revision and Junos version.
2. Check interface inventory and supported port modes.
3. Confirm the physical interfaces are free and that the LAG is supported in the selected port mode.
4. Review all documentation prefixes and use them only in an isolated lab.
5. Ensure console or out-of-band access is available.

## Initial checks

    show chassis hardware
    show version
    show interfaces terse
    show chassis fpc pic-status

## Configuration review

Load the example into a lab candidate configuration only. Do not paste it into a production router as-is.

    show | compare
    show configuration system | display set
    show configuration interfaces | display set
    show configuration logical-systems | display set
    show configuration protocols bgp | display set
    show configuration policy-options | display set
    commit check

## Interfaces and LAG

    show interfaces terse
    show interfaces ae0 extensive
    show lacp interfaces
    show interfaces diagnostics optics

## Routing and BGP

    show route summary
    show route 203.0.113.0/24 exact
    show route protocol bgp
    show bgp summary
    show bgp neighbor
    show route receive-protocol bgp 198.51.100.2
    show route advertising-protocol bgp 198.51.100.2

## Logical systems

    show logical-systems
    show route logical-system CDN-LS
    show bgp summary logical-system CDN-LS
    show interfaces terse logical-system CDN-LS

## Policer counters

    show firewall policer
    show interfaces ae0.100 extensive
    show interfaces ae0.200 extensive

Command availability and exact syntax may vary by Junos release. Use CLI help on the target device.

## Safe commit workflow

For a remote change, use a confirmed commit and maintain a rollback path:

    configure
    load set terminal
    # Paste only the reviewed lab configuration into a lab device.
    show | compare
    commit check
    commit confirmed 5

After confirming reachability and expected routing behavior:

    commit

If management access or forwarding is lost before confirmation, the confirmed commit should automatically roll back after its timer expires. Do not rely on this instead of console/OOB access.

## Rollback

    configure
    rollback 1
    show | compare
    commit check
    commit confirmed 5

Only finalize the rollback after checking service impact.

## Important limitations

- This example has not been committed on an MX204 or run through Juniper commit-check.
- Physical port names, LAG member syntax, logical-tunnel support, logical-system feature support, policer attachment, and BGP options must be validated against the actual Junos release and hardware.
- eBGP peer examples need matching remote-side configuration and reachable link addressing before sessions can establish.
- The master and logical-system iBGP example is a design illustration. Confirm address reachability and local/remote AS behavior before enabling it.
- Documentation prefixes must never be advertised to the public Internet.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
