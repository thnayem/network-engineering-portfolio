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

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
