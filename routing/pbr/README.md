# Juniper MX204 Policy-Based Routing (PBR) Lab

**Platform:** MX204 / Junos | **Type:** Original sanitized example

## Objective
Steer packets sourced from 10.10.10.0/24 and entering et-0/0/3.0 through a dedicated forwarding routing-instance and alternate uplink. Other traffic uses normal routing.

## Topology
LAN host 10.10.10.10/24 -> MX204 et-0/0/3.0 (10.10.10.1/24) -> PBR-ISP2 -> et-0/0/4.0 (198.51.100.9/30) -> test next-hop 198.51.100.10.

## Files
- [Full PBR configuration](./mx204-pbr.set.example)
- [Design and command explanations](./design-and-explanations.md)
- [Verification and rollback](./verification-and-rollback.md)

The filter is applied inbound on the LAN interface. Private/documentation destinations are bypassed before the source-prefix PBR match. All addresses are fictional lab values; validate the design and Junos syntax before deployment.
