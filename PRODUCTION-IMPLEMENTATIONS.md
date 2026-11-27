# Production Engineering Demonstrations

## Hands-on production infrastructure experience

I have extensive hands-on experience working with live production infrastructure and carrying out remote operational tasks across servers, routers, and switches. This includes:

- Remote configuration and administration of production servers and network devices.
- Router and switch configuration, service changes, routing/switching maintenance, and troubleshooting.
- Server maintenance, configuration updates, software/OS upgrade activities, and fault isolation.
- Planned upgrades and maintenance with impact assessment, backup, rollback preparation, and post-change verification.
- Remote incident response, root-cause investigation, service restoration, and coordination with relevant teams or vendors.

These are operational experience areas. The public configuration files below are sanitized technical references and are not represented as complete production backups or as proof that every published example was deployed unchanged.

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

## Remote operations and change discipline

Remote production work requires controlled access and a clear recovery path. A typical workflow includes:

1. Confirm authorization, maintenance window, impact, and out-of-band or alternate access where available.
2. Capture the current configuration and operational state.
3. Review dependencies, platform/software compatibility, and expected service impact.
4. Prepare and peer-review the change and rollback plan.
5. Apply one controlled change at a time.
6. Verify device health, routing, switching, server services, monitoring, and user/application reachability.
7. Record the outcome, evidence, and follow-up actions.

## How to interpret the files

- **Implementation reference:** A reduced explanation of a design or operational method I have worked with. It is not a complete configuration export.
- **Lab example:** A separately written example used to explain a technical concept. It should not be read as proof that the exact sample was deployed in production.
- **Verification guide:** Suggested checks and change-safety steps. Commands may need adjustment for the target release and hardware.

The README in each platform directory is the source of truth for that directory's scope. Where a file is incomplete or illustrative, that limitation should be stated beside the example.

## Confidentiality

The public material uses neutral labels and documentation-only addressing. It must not be used to infer an employer, customer, provider, site, or live network topology. No original operational backup, customer list, credentials, or private network inventory is intended to be part of this repository.

## Validation boundary

The examples have not all been checked by a vendor parser or committed on the named hardware. Review syntax, feature support, interface dependencies, routing behavior, and rollback steps in an isolated lab before using any part of them. A successful secret scan does not establish technical correctness or legal permission to publish source-derived material.

---

**Authorship and AI assistance:** The technical work, decisions, troubleshooting, lab activity and production experience described in this document are my own. I use AI as a practical writing and productivity aid for editing wording, organizing structure and preparing formal templates or disclaimers. AI does not replace or generate my technical skills, hands-on work or professional judgement. I review and take responsibility for what I publish.
