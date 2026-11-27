# MX204 PBR: Design and Explanation

## Objective
Steer packets from 10.10.10.0/24 entering et-0/0/3.0 into forwarding routing-instance PBR-ISP2. Other traffic follows the master routing table.

## Topology and roles
- LAN ingress: et-0/0/3.0, 10.10.10.1/24.
- Dedicated PBR egress: et-0/0/4.0, 198.51.100.9/30.
- Test next-hop: 198.51.100.10.
- Forwarding table: PBR-ISP2.inet.0.

## How it works
1. The forwarding instance owns the alternate uplink and a default route via 198.51.100.10.
2. LAN-PBR is applied inbound on the LAN interface.
3. BYPASS terms exempt private and documentation destinations from steering.
4. SELECT-ISP2 matches the LAN source prefix, increments a counter, and selects PBR-ISP2.
5. NORMAL-ROUTING accepts all remaining traffic for ordinary routing.

Filter term order is important. A broad match placed before bypass terms can steer traffic unintentionally.

## Design considerations
PBR is stateless steering, not stateful firewalling. Ensure the return path exists and is symmetric where required. Add explicit exemptions for management, internal services, monitoring, and other destinations that must not use the alternate uplink. Validate next-hop resolution in the forwarding instance and confirm feature support on the target Junos release.

All addresses are lab values. Do not paste this into production without a complete traffic-flow and rollback plan.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
