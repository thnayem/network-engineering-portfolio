# Cisco 7606-S: Design Notes

## Scope

These notes explain the Cisco 7606-S configuration examples in this directory. They use an IOS 15.5-era command style and documentation-only values. The files show selected parts of a design; they are not a complete device configuration.

## VRF separation

The examples use separate VRFs for service and management traffic. Route-targets describe route import and export policy, but route-targets alone do not create route leaking in a VRF-Lite design. Any inter-VRF route exchange needs an explicit, supported mechanism and policy.

## VLAN handoffs and EtherChannel

Routed subinterfaces use 802.1Q tags to separate handoffs. The bundle uses `channel-group 5 mode on`, which creates a static EtherChannel. It does not negotiate LACP. Both ends need matching bundle and member-interface settings.

## BGP and route policy

The configuration segments illustrate BGP address-families, peer policy, prefix filtering, route-maps, and selective route advertisement. Review the actual prefix lists and route-map sequence before adapting the example. A policy that is syntactically valid can still advertise or reject the wrong routes.

## Policy-Based Routing

The PBR example matches selected traffic and directs it to a policy-selected path. Check next-hop reachability, route resolution, and the return path. Test traffic that matches the policy as well as traffic that should continue through normal routing.

## QoS and monitoring

The examples show policing and service-policy structure, along with SPAN/RSPAN and NetFlow concepts. Numeric values are illustrative and should not be treated as actual service allocations.

## Spanning tree

The reference documents PVST. Rapid-PVST+ is a different mode and should be shown as a separate example if added.

## Platform checks

Cisco 7606-S behavior depends on the supervisor, line cards, IOS image, licenses, and forwarding hardware. Check command support and hardware restrictions on the exact platform. The examples have not been validated on a live 7606-S; test them in an isolated environment first.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
