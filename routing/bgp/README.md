# BGP Labs and Engineering Notes

BGP protocol references and independently authored lab examples. The examples use fictional ASNs and documentation-only prefixes.

## Start here

- [Dual-ISP BGP Traffic Engineering Lab](./dual-isp-traffic-engineering-lab.md) - eBGP peers, import/export filtering, Local Preference, AS-PATH prepending, communities, failover and verification.
- [Basic eBGP session lab](./README.md) - a minimal Cisco IOS and Junos peer configuration reference.
- [Juniper MX204 BGP policy lab](../bgp-policy/README.md) - prefix allow-lists, local preference, communities, AS-path prepend, explicit reject terms and rollback.

## Learning path

1. Establish peer reachability and understand the BGP finite-state machine.
2. Configure eBGP and verify the session.
3. Understand received, accepted, selected and advertised routes as separate stages.
4. Apply explicit import/export policy using prefix lists and policy terms.
5. Compare Local Preference, AS-PATH, MED, communities and next-hop handling.
6. Test primary/backup behaviour and verify the actual forwarding path.
7. Review route-leak prevention, maximum-prefix, RPKI/IRR, peer security and rollback.

## Operational checks

- Peer state and uptime.
- Received/accepted/advertised prefix counts.
- Import and export policy attachment.
- Best-path attributes and next-hop reachability.
- Routing table and forwarding table.
- Service reachability and return path.
- Logs, reset counters and convergence evidence.

## Evidence and validation

The traffic-engineering page is an independent lab/demo reference, not a production configuration. It has not been claimed as emulator- or hardware-validated. Record the exact platform/release and actual results before marking the lab tested.

Production experience described in the parent portfolio is separate from the validation status of these public examples.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
