# Case Study: Multi-site NTTN Connectivity Operations

**Focus:** Enterprise WAN operations, provider coordination, fault isolation and service verification  
**Environment:** Multi-site enterprise connectivity  
**Disclosure:** Sanitized summary; no provider, site, circuit, addressing or contract details are published.

## Operational context

Multi-site connectivity depends on the transport provider, physical handoff, local network equipment, routing, and the applications using the link. A fault may originate in the provider transport, the customer handoff, an interface or VLAN, routing, or the destination service.

My operational experience includes working with multi-site NTTN connectivity, coordinating with service providers, following up on faults and service levels, and supporting network-side troubleshooting.

## Operational responsibilities

- Coordinate link activation, service changes, fault follow-up and maintenance with NTTN/provider teams.
- Work with internal network and site stakeholders to establish impact, ownership and next actions.
- Review the physical and logical handoff, interface state, VLAN, addressing, routing and end-to-end reachability.
- Use available monitoring and device counters to help isolate loss, errors, latency or reachability problems.
- Track provider updates and agreed response/restoration commitments.
- Verify service from the network side after restoration and communicate any remaining issues.

## Troubleshooting and coordination approach

1. Establish the affected sites, services, start time and business impact.
2. Check local equipment, interface state, optics where applicable, counters, VLAN handoff and local power/physical dependencies.
3. Verify addressing, gateway reachability, routing adjacencies and the expected return path.
4. Compare local observations with provider status and request transport-side investigation when the evidence points beyond the local demarcation.
5. Maintain a clear incident timeline, provider reference in approved internal records, escalation and next update.
6. After restoration, validate end-to-end reachability and critical service paths, review monitoring, and document outstanding corrective actions.

## Operational controls

- Follow approved change and maintenance windows.
- Preserve current configuration and a rollback path before planned changes.
- Avoid changing multiple network layers at once during fault isolation.
- Confirm service restoration rather than relying only on a provider's closure message.
- Keep actual circuit IDs, contracts, provider contacts and topology in access-controlled internal systems.

## Outcome and evidence

This case study documents the operational scope and method; it intentionally does not claim a specific uptime improvement, restoration time, or SLA percentage.

To strengthen this evidence when disclosure is approved, add:
- A redacted topology showing only fictional site labels and documentation-only IP ranges.
- Sanitized interface, routing-neighbor or monitoring output.
- A redacted incident/change timeline with verified timestamps.
- A measured result only when supported by approved records.

## Skills demonstrated

Enterprise WAN operations, NTTN/provider coordination, incident ownership, routing and switching troubleshooting, service verification, SLA follow-up, stakeholder communication and change discipline.
