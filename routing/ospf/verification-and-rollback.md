# MX204 OSPF: Verification and Rollback

## Candidate
    configure
    show | compare
    commit check
    commit confirmed 5
Confirm adjacency and route learning, then commit.

## Verify
    show ospf interface
    show ospf neighbor
    show ospf database
    show route protocol ospf
    show route 192.0.2.2/32 exact
    ping 10.0.12.2 source 10.0.12.1
    ping 192.0.2.2 source 192.0.2.1

Expected: et-0/0/5.0 in area 0; neighbor Full; remote loopback learned if advertised.

## Rollback
    configure
    rollback 1
    show | compare
    commit check
    commit confirmed 5

Keep OOB access. Verify command syntax on the installed Junos release.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
