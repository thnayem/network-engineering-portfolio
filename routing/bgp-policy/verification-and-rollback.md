# MX204 BGP Policy: Verification and Rollback

## Candidate validation
    configure
    show | compare
    commit check
    commit confirmed 5

## Verify
    show bgp summary
    show bgp neighbor 198.51.100.2
    show route receive-protocol bgp 198.51.100.2
    show route advertising-protocol bgp 198.51.100.2
    show route 203.0.113.0/24 exact
    show configuration policy-options | display set
    show policy TRANSIT-IN
    show policy TRANSIT-OUT

Confirm the actual received and advertised route sets. A configured policy alone does not prove the session is established or a route is eligible.

## Rollback
    configure
    rollback 1
    show | compare
    commit check
    commit confirmed 5

Never test export policy against a live peer without approved prefixes and change authorization.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
