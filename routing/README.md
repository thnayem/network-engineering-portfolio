# Routing Labs

**Production operations:** Hands-on remote configuration, maintenance, upgrades, and troubleshooting of live production routing infrastructure, including BGP, OSPF, static routing, route policy, failover, and tunnel-based connectivity.

- [OSPF](./ospf/)
- [BGP](./bgp/) - eBGP fundamentals, dual-ISP traffic engineering, route policy and failover labs
- [BGP policy, communities and prefix filtering](./bgp-policy/)
- [Policy-Based Routing](./pbr/)
- [Routing policy and prefix filtering](./policy/)
- [Static routing](./static-routing/)

## Operational verification

- Confirm physical/underlay reachability before investigating routing adjacencies.
- Review BGP/OSPF neighbor state, timers, authentication, route exchange, filters, next-hop reachability, and routing-table installation.
- Check convergence, preferred/backup paths, asymmetric routing, and service impact.
- For remote changes, preserve management reachability, capture the pre-change state, and prepare rollback before applying policy or protocol changes.

All addresses and ASNs are documentation-only examples. Vendor syntax is illustrative and must be validated on the target release. Production experience is distinct from the validation status of these published labs.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
