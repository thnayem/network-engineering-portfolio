# Juniper MX240: Design Notes

## Scope

This document explains the configuration patterns shown in the MX240 example. The reference uses Junos 18.2R3-S5.3-style set commands and is kept separate from the MX204 material.

## Chassis and port settings

The sample includes an aggregated Ethernet device-count setting, tunnel-services bandwidth, and example PIC port speeds. These are platform-dependent settings. Confirm the installed FPC/PIC model and supported port modes before using them.

## Logical systems and logical tunnels

The example uses two logical systems with neutral names. A pair of logical-tunnel units provides an interconnect between their routing contexts. Interface ownership, unit pairing, addressing, and routing must agree on both sides.

The sample assigns routing identities to both logical systems. The BGP examples are deliberately small and should be reviewed as a design illustration rather than a complete peering configuration.

## Aggregated Ethernet service interface

A VLAN-tagged unit on an aggregated Ethernet interface represents a routed service handoff. The example uses documentation-only addressing and a fictional VLAN ID. It does not include the physical member interfaces or the complete switching path.

## BGP policy

The import policy accepts the default route from the example peer and rejects other routes. The export policy permits the directly connected lab handoff and rejects the rest. This is intentionally restrictive for demonstration purposes.

Before using a similar policy, confirm the intended route set, protocol match conditions, policy evaluation order, and the routes actually eligible for advertisement.

## Policer

The example policer uses illustrative bandwidth and burst values. They are not operational service allocations. A policer must be attached at the correct interface or filter point for it to affect traffic.

## Validation boundary

This excerpt has not been loaded on an MX240 and has not passed a Juniper commit check. Hardware support, FPC/PIC settings, logical-system syntax, interface dependencies, BGP reachability, and policy behavior all require validation on the target platform and release.

All identifiers and addresses in the public example are fictional.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
