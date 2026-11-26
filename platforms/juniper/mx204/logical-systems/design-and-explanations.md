# MX204 Logical Systems: Architecture and Explanation

## Purpose
A logical system is a separate logical router context on supported Juniper platforms. It can isolate interfaces, routing protocols, route tables, policies, and operational state, subject to hardware and release limits.

## Master context
The master uses loopback 192.0.2.1/32, AS 65010, and logical-tunnel unit lt-0/0/0.500 at 10.255.0.1/30.

## CDN-LS
CDN-LS uses loopback 192.0.2.20/32, the same AS 65010, and peer logical-tunnel unit .501 at 10.255.0.2/30. Same AS means the master-to-LS BGP relationship is iBGP.

## Loopback reachability
Static routes in both contexts point the remote loopback through the directly connected logical-tunnel peer. Each BGP side sources from its own loopback. For larger networks, assess IGP reachability, next-hop handling, route leaking, and policy boundaries rather than scaling static routes indefinitely.

## VLAN handoffs
VLAN 100 and 200 are represented as L3 units on ae0 inside CDN-LS. Confirm the physical aggregate, logical-system ownership, encapsulation, and feature support for the exact MX204/Junos release.

Logical systems are not a substitute for physical security boundaries. Check scale, resource allocation, control-plane protection, and management access.
