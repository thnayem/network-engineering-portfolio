# MX204 Logical Systems: Verification and Rollback

## Candidate
    configure
    show | compare
    commit check
    commit confirmed 5

## Verify
    show logical-systems
    show interfaces terse
    show interfaces terse logical-system CDN-LS
    show route
    show route logical-system CDN-LS
    show bgp summary
    show bgp summary logical-system CDN-LS
    show route logical-system CDN-LS 192.0.2.1/32 exact

Confirm both logical-tunnel units are up, loopbacks are reachable in both contexts, and iBGP reaches Established.

## Rollback
    configure
    rollback 1
    show | compare
    commit check
    commit confirmed 5

Validate exact command options on the installed Junos release. Keep console/OOB access during logical-system interface or routing changes.
