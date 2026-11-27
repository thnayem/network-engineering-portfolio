# Juniper MX204 Firewall Filter Lab

Stateless filter examples for routing-engine protection, management-plane source restrictions, BGP/OSPF control traffic, counters, and service-interface ingress filtering.

- [Configuration](./mx204-firewall-filters.set.example)
- [Design and explanation](./design-and-explanations.md)
- [Topology and packet flow](./topology-and-packet-flow.md)
- [Verification and rollback](./verification-and-rollback.md)

Warning: an incorrect lo0 input filter can lock out management and routing protocols. The example attachment is commented until all required services are reviewed.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
