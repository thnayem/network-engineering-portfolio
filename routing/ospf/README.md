# Juniper MX204 OSPF Lab

Single-area OSPF backbone example between an MX204 and a lab core router.

## Topology
MX204 lo0.0: 192.0.2.1/32; et-0/0/5.0: 10.0.12.1/30. Remote LAB-CORE: 10.0.12.2/30 with loopback 192.0.2.2/32. Both sides use area 0.0.0.0.

## Files
- [Complete OSPF configuration](./mx204-ospf.set.example)
- [Design and command explanations](./design-and-explanations.md)
- [Verification and rollback](./verification-and-rollback.md)

The loopback is passive and the routed link is point-to-point. Configure matching area, timers, and authentication on the neighbor. All addresses are fictional.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
