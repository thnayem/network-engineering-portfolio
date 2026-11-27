# Connectivity, NTTN, and Data Center Operations

A practical operations reference covering multi-site enterprise connectivity, NTTN service coordination, organization-owned fiber infrastructure, and Data Center (DC) / Disaster Recovery (DR) connectivity.

This section documents operational responsibilities, design considerations, coordination workflows, and verification practices. It reflects hands-on operational work involving live production connectivity, remote router/switch configuration, upgrades, maintenance, troubleshooting, NTTN/vendor coordination, dark-fiber infrastructure, and DC/DR service continuity. Public examples intentionally use generic labels and do not disclose provider names, circuit IDs, real site details, IP addresses, or confidential topology.

## Hands-on production connectivity operations

Operational responsibilities include remote configuration and maintenance of production routers and switches, tunnel and routing troubleshooting, coordinating carrier/NTTN teams, monitoring service performance against agreed SLAs, managing organization-owned fiber fault/restoration activities, and coordinating DC/DR ports, bandwidth, routing, VPNs, and maintenance windows. Changes should follow authorization, impact assessment, backup, rollback, and post-change verification procedures.

## 1. OSPF over GRE tunnels

Use case: extend Layer 3 reachability and dynamic routing between separated sites across an IP underlay.

Key design and operational points:

- Establish underlay reachability between GRE tunnel source and destination addresses.
- Configure tunnel addressing and ensure the tunnel endpoints are reachable independently of routes learned through the tunnel.
- Enable OSPF on the tunnel interface and define the correct area, network type, timers, and authentication policy where supported.
- Set a suitable tunnel MTU and review IP fragmentation or TCP MSS behavior.
- Prevent recursive routing by ensuring tunnel destination routes resolve through the intended underlay.
- Validate OSPF neighbor state, database exchange, learned routes, path selection, and return traffic.
- Monitor tunnel state, packet loss, latency, jitter, and route convergence.

GRE does not encrypt traffic. Where confidentiality is required, protect GRE with IPsec or use an appropriate secure VPN design. See [Tunnel Technologies](../tunnels/) and [VPN Technologies](../vpn/).

## 2. Multi-site connectivity over NTTN

NTTN (National Telecommunication Transmission Network) connectivity can provide transport between geographically distributed offices, branches, campuses, and data centers.

Operational scope:

- Coordinate site-to-site transport requirements, bandwidth, handoff type, demarcation, and service activation with the NTTN provider.
- Maintain a site/circuit inventory using sanitized identifiers in public documentation.
- Validate end-to-end Layer 2 or Layer 3 handoff, VLAN tagging, IP addressing, routing, MTU, and redundancy as applicable.
- Coordinate primary and backup paths and confirm failover behavior.
- Test reachability and application paths from both ends after provisioning or change.
- Track utilization, latency, packet loss, jitter, interface errors, and service availability.

## 3. NTTN vendor coordination and SLA management

A structured provider coordination process helps maintain service quality and accountability.

### Vendor coordination workflow

1. Raise service requests for new links, bandwidth upgrades, relocations, or fault resolution.
2. Confirm scope, site readiness, demarcation point, handoff, committed bandwidth, and delivery timeline.
3. Coordinate provider field teams, internal network teams, facility teams, and relevant stakeholders.
4. Record ticket/reference numbers, incident timestamps, updates, escalation contacts, and restoration details.
5. Verify service restoration independently before closing an incident.
6. Maintain a record of recurring faults and follow up on corrective and preventive actions.

### SLA monitoring

Track the contractually agreed service targets rather than assuming a universal SLA:

- Availability / uptime
- Fault acknowledgement and response time
- Restoration time / MTTR
- Committed bandwidth and throughput
- Latency, jitter, and packet loss where specified
- Planned maintenance notifications
- Escalation and service-credit process, where applicable

Maintain evidence such as monitoring graphs, interface counters, timestamps, provider ticket updates, test results, and outage summaries. Compare performance against the actual contract and agreed measurement method.

## 4. Organization-owned dark-fiber / core cable maintenance

Operational considerations for maintaining organization-owned fiber routes and core cable infrastructure:

- Keep route records, splice/closure locations, patch-panel mapping, fiber-core allocation, and endpoint records in an access-controlled inventory.
- Coordinate planned civil works, route inspections, duct/chamber access, and maintenance windows.
- Inspect optical levels and link health at both ends; use suitable optical testing and fault-location procedures when required.
- Track fiber cuts, degradation, high-loss events, splice repairs, and restoration history.
- Maintain spare-core planning, protection/diverse routing where available, and escalation contacts.
- Verify optical power, interface state, error counters, and end-to-end service after repair.

Do not publish actual cable routes, chamber locations, core maps, facility details, or security-sensitive infrastructure records in a public repository.

## 5. DC / DR connectivity and infrastructure operations

Coordinate connectivity between the primary Data Center (DC), Disaster Recovery (DR) site, and connected enterprise locations.

### Port and bandwidth management

- Coordinate rack/patch-panel, switch/router port, cross-connect, VLAN, and handoff requirements with DC/DR facility and service providers.
- Track port capacity, speed, duplex, optics, utilization, committed bandwidth, and planned expansion.
- Validate interface status, optical levels, errors, MTU, VLAN tagging, and end-to-end throughput after provisioning or change.

### Tunnels, routing, and VPN

- Maintain and troubleshoot GRE/IPsec or other approved tunnel connectivity between DC, DR, and remote sites.
- Operate and verify BGP and OSPF adjacencies according to the approved routing design.
- Validate route advertisements, prefix filters, next-hop reachability, failover preference, and return paths.
- Maintain site-to-site VPN connectivity, encryption/security association status, peer reachability, and access policies.
- Confirm that DC/DR application networks and required services are reachable over the intended primary or backup path.

### DC/DR maintenance and coordination

- Coordinate planned maintenance with facility operations, NTTN/vendor teams, network teams, system/application owners, and business stakeholders.
- Review impact, dependencies, maintenance windows, communication plan, rollback plan, and recovery objectives before changes.
- Verify power/environmental or facility notifications through the responsible DC/DR operations team; keep network checks aligned with facility procedures.
- Perform pre- and post-maintenance checks for links, routing adjacencies, tunnels, VPNs, bandwidth, monitoring, and critical application reachability.
- Document incidents, changes, test evidence, action owners, and follow-up dates.

## 6. Operational verification checklist

| Area | Verification |
|---|---|
| Physical / fiber | Link state, optics, light levels, fiber path, interface errors |
| Transport / NTTN | Handoff, VLAN, bandwidth, latency, packet loss, provider ticket status |
| GRE tunnel | Source/destination reachability, tunnel state, MTU, counters |
| OSPF | Neighbor state, area, database, route installation, convergence |
| BGP | Session state, advertised/received prefixes, filters, next-hop |
| VPN / IPsec | Peer identity, IKE/IPsec SAs, selectors, encryption counters |
| DC / DR | Port mapping, cross-connect, capacity, path redundancy, service reachability |
| SLA | Availability, response/restoration times, evidence, escalation status |
| Change control | Approval, impact, maintenance window, rollback, post-checks |

## 7. Documentation and security boundaries

- Use fictional site names, documentation-only IP ranges, and sanitized circuit references in public examples.
- Never publish provider contracts, SLA documents, circuit IDs, customer details, real fiber maps, DC rack layouts, credentials, private keys, or unredacted configurations.
- Keep operational records and detailed topology in approved internal systems with role-based access.
- Distinguish design examples from production-validated configurations. Validate all commands against the exact platform and software release before implementation.

This repository section is a vendor-neutral operational reference. It does not disclose confidential infrastructure details or claim that the examples have been validated on a live production network.
