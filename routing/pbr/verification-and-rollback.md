# MX204 PBR: Verification and Rollback

## Pre-checks
    show version
    show interfaces terse et-0/0/3
    show interfaces terse et-0/0/4
    show route table PBR-ISP2.inet.0

## Safe candidate workflow
    configure
    show | compare
    commit check
    commit confirmed 5

After testing management access and a single lab client:
    commit

## Verify
    show configuration routing-instances PBR-ISP2 | display set
    show configuration firewall family inet filter LAN-PBR | display set
    show firewall filter LAN-PBR
    show route table PBR-ISP2.inet.0
    show route forwarding-table

Generate traffic from 10.10.10.0/24. Confirm PBR-ISP2-TRAFFIC increments and the selected path uses 198.51.100.10. Verify return routing independently.

## Rollback
    configure
    rollback 1
    show | compare
    commit check
    commit confirmed 5

A wrong ingress filter or missing return route can interrupt connectivity. Keep console/OOB access available.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
