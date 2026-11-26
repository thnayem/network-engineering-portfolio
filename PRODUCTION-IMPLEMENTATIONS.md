# Production Engineering Demonstrations

## What this section represents

The Cisco 7606-S, Juniper MX204, and Juniper MX240 sections describe network engineering work and implementation patterns I have handled. I have reduced and rewritten the public material so it can be reviewed without exposing an organization's network details.

These pages are not copies of complete device configurations. They show selected design and operational ideas, with fictional names, addresses, and other identifiers. They are intended to explain the work, not to serve as deployment files.

## Cisco 7606-S

The Cisco reference focuses on core routing and service separation:

- VRFs and route-target relationships
- 802.1Q routed subinterfaces and Port-channel handoffs
- Static EtherChannel using `channel-group 5 mode on`
- BGP IPv4/IPv6 policy, prefix-lists, and route-maps
- Policy-Based Routing
- QoS policing and interface service policies
- PVST, VLAN handling, SPAN/RSPAN, and monitoring

The documented bundle is static EtherChannel, not LACP. The spanning-tree reference is PVST; it should not be described as Rapid-PVST+.

See [the Cisco 7606-S section](./platforms/cisco/7606s/).

## Juniper MX204

The MX204 material is maintained separately from the MX240 material. It covers logical systems, logical-tunnel connectivity, aggregated Ethernet, BGP policy, static routing, firewall filters, filter-based forwarding, and service policing.

See [the Juniper MX204 section](./platforms/juniper/mx204/).

## Juniper MX240

The MX240 reference uses Junos 18.2R3-S5.3-style set commands. It illustrates logical systems, logical tunnels, aggregated Ethernet service units, BGP import/export policy, and chassis configuration patterns.

It is a reduced excerpt. It does not include every dependency or every configuration element needed to build a complete router configuration.

See [the Juniper MX240 section](./platforms/juniper/mx240/).

## How to interpret the files

- **Implementation reference:** A reduced explanation of a design or operational method I have worked with. It is not a complete configuration export.
- **Lab example:** A separately written example used to explain a technical concept. It should not be read as proof that the exact sample was deployed in production.
- **Verification guide:** Suggested checks and change-safety steps. Commands may need adjustment for the target release and hardware.

The README in each platform directory is the source of truth for that directory's scope. Where a file is incomplete or illustrative, that limitation should be stated beside the example.

## Confidentiality

The public material uses neutral labels and documentation-only addressing. It must not be used to infer an employer, customer, provider, site, or live network topology. No original operational backup, customer list, credentials, or private network inventory is intended to be part of this repository.

## Validation boundary

The examples have not all been checked by a vendor parser or committed on the named hardware. Review syntax, feature support, interface dependencies, routing behavior, and rollback steps in an isolated lab before using any part of them. A successful secret scan does not establish technical correctness or legal permission to publish source-derived material.
