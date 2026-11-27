# Case Study: Data Centre and Disaster Recovery Connectivity Operations

**Focus:** DC/DR network connectivity, service coordination and maintenance verification  
**Environment:** Primary Data Centre and Disaster Recovery connectivity  
**Disclosure:** Sanitized summary; no facility, provider, rack, cross-connect, circuit, addressing or topology details are published.

## Operational context

Data Centre and Disaster Recovery services depend on reliable physical connectivity, correctly provisioned ports and bandwidth, cross-connects, routing, VPNs/tunnels, and coordination between facility, network, system and service teams.

My operational experience includes coordinating DC/DR connectivity requirements and maintenance activities involving ports, bandwidth, cross-connects, BGP/OSPF, VPNs and tunnels.

## Operational responsibilities

- Coordinate port, bandwidth, handoff and cross-connect requirements with relevant DC/DR and service-provider teams.
- Support routing and tunnel connectivity checks, including BGP, OSPF, VPN and GRE/IPsec-related paths where applicable.
- Work with network, system, application and facility stakeholders during planned maintenance and service incidents.
- Review service dependencies, maintenance impact, communication and rollback requirements.
- Perform or coordinate pre-change and post-change connectivity checks.

## Maintenance and verification approach

1. Confirm the approved scope, affected services, stakeholders, maintenance window and change owner.
2. Check port status, speed, optics where applicable, VLAN/handoff, interface counters and expected bandwidth.
3. Verify routing adjacencies, advertised/received routes, next-hop reachability and return paths.
4. Check tunnel and VPN peer state, security associations and traffic counters where relevant.
5. Validate reachability between the required DC/DR networks and the critical service endpoints.
6. Confirm monitoring visibility and communicate the outcome, outstanding risks and follow-up actions.
7. Keep the change record, evidence and rollback notes in the organization's approved systems.

## Risk and continuity controls

- Do not assume that a physically active link proves application-level service availability.
- Check both directions and the expected primary/backup path.
- Confirm route filtering and failover behavior against the approved design.
- Coordinate facility-related work with the responsible DC/DR operations team.
- Do not make unapproved changes to production routing, security policy or cross-connects.
- Protect actual facility details, rack layouts, port maps and network diagrams.

## Outcome and evidence

This document describes operational responsibilities and a repeatable verification approach. It does not claim a particular DR test result, recovery time, uptime improvement, or failover success rate.

To add stronger proof, publish only approved and redacted material such as:
- A logical DC/DR diagram using fictional labels and documentation-only IP ranges.
- Sanitized BGP/OSPF neighbor and route verification.
- Redacted interface/tunnel status before and after a maintenance window.
- A change summary with verified checks and confirmed service-owner sign-off.
- Measured RTO/RPO or failover results only when supported by an approved test record.

## Skills demonstrated

Data Centre and DR connectivity coordination, routing operations, VPN/tunnel troubleshooting, vendor coordination, maintenance planning, risk awareness, service validation and stakeholder communication.
