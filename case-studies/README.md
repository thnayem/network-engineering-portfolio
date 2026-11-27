# Infrastructure Operations Case Studies

This section brings together selected examples of network work, troubleshooting and lessons learned. I have kept employer, provider and customer details out of these pages.

## Published case studies

- [Multi-site NTTN connectivity operations](multi-site-nttn-connectivity.md) — provider coordination, fault isolation, service checks, SLA follow-up and restoration verification.
- [Data Centre and Disaster Recovery connectivity operations](dc-dr-connectivity-operations.md) — port and bandwidth coordination, cross-connects, routing, VPN/tunnel checks and maintenance coordination.
- [OSPF over GRE for multi-site connectivity](ospf-over-gre-multisite-routing.md) — a sanitized summary of the work area, underlay/overlay architecture, operational checks and risks.
- [OSPF over GRE - Complete Lab Walkthrough](ospf-over-gre-lab-walkthrough.md) — a fictional two-router lab with IOS-style configuration, verification commands, troubleshooting, MTU and rollback.

## Architecture references

- [Enterprise multi-site overlay architecture](../network-architecture/enterprise-multisite-overlay-reference.md) — an illustrative underlay, GRE overlay, OSPF, resilience and operations reference.

## A note about evidence

Some pages describe work I have been involved in; the lab walkthrough is an independent example. I do not want to blur those two things. Where I can share evidence, I prefer a redacted monitoring graph, a sanitized command output, a diagram using documentation-only addresses or a clear post-change check.

I will not publish raw configurations, credentials, customer data, provider tickets, contracts or internal screenshots without permission. I also will not add uptime improvements, MTTR reductions, bandwidth gains or project savings unless I can verify the figures and am allowed to share them.

---

**Authorship and AI assistance:** The technical work, decisions, troubleshooting, lab activity and production experience described in this document are my own. I use AI as a practical writing and productivity aid for editing wording, organizing structure and preparing formal templates or disclaimers. AI does not replace or generate my technical skills, hands-on work or professional judgement. I review and take responsibility for what I publish.
