# Cisco 7606-S Core Routing Example

## Overview

This section documents Cisco 7606-S routing and switching work I have handled. The examples use an IOS 15.5-era configuration style and focus on the parts of the design that are useful to explain publicly.

The files are shortened and use fictional values. They are not a complete router backup and are not ready to load onto a live device.

## Topics

- VRF separation and route-target design
- 802.1Q routed subinterfaces and Port-channel handoffs
- Static EtherChannel with `channel-group 5 mode on`
- BGP IPv4/IPv6, prefix-lists, and route-maps
- Policy-Based Routing
- QoS policing
- PVST, VLAN handling, SPAN/RSPAN, and monitoring

## Files

- [Integrated configuration example](./cisco-7606s-integrated-demo.cfg.example)
- [Design notes](./design-and-explanations.md)
- [Topology and packet flow](./topology-and-packet-flow.md)
- [Verification and rollback](./verification-and-rollback.md)

## Configuration segments

- [VRF segmentation](./segments/01-vrf-segmentation.cfg.example)
- [VLAN and EtherChannel](./segments/02-vlan-etherchannel.cfg.example)
- [BGP policy](./segments/03-bgp-policy.cfg.example)
- [PBR](./segments/04-pbr.cfg.example)
- [QoS](./segments/05-qos.cfg.example)
- [IPv6 and monitoring](./segments/06-ipv6-monitoring.cfg.example)
- [Layer 2 controls](./segments/07-layer2-security.cfg.example)

## Notes before use

The EtherChannel example is static; it does not use LACP. The spanning-tree example documents PVST, not Rapid-PVST+. Keep those distinctions when comparing or extending the configuration.

Feature support depends on the supervisor, line cards, IOS image, and licenses. Check the exact platform and release, then test in an isolated lab before using any command on a live device.
