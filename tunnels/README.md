# Tunnel Technologies

A practical reference for common routed and remote-access tunneling technologies used in enterprise and service-provider networks.

## Coverage

| Technology | Purpose | Key considerations |
|---|---|---|
| **GRE (Generic Routing Encapsulation)** | Encapsulates Layer 3 traffic inside an IP packet and can carry multicast or dynamic-routing traffic across an IP network. | GRE does not encrypt traffic by itself. Plan tunnel source/destination reachability, MTU, routing, and keepalives where supported. |
| **IPsec** | Protects IP traffic with authentication, integrity, and encryption. Commonly used for site-to-site VPNs and as the security layer for other tunnels. | Define IKE version and proposals, peer identity, authentication, traffic selectors, lifetimes, NAT-T, and rekey behavior consistently at both ends. |
| **L2TP (Layer 2 Tunneling Protocol)** | Tunnels PPP sessions over an IP network, commonly for remote-access or provider access scenarios. | L2TP alone does not provide encryption. Use L2TP/IPsec when confidentiality and peer authentication are required. |
| **L2TP/IPsec** | Combines L2TP for PPP session tunneling with IPsec for protection. | Check UDP 500/4500 and UDP 1701 handling, NAT traversal, PPP authentication, address assignment, and MTU/MSS. |

## Design and packet-flow notes

- **GRE over IPsec:** GRE provides the tunnel interface and routing flexibility; IPsec protects the GRE packets between tunnel endpoints.
- **Route-based IPsec:** Uses a virtual tunnel interface where supported. Routing determines which traffic enters the protected tunnel.
- **Policy-based IPsec:** Uses matching traffic selectors or crypto policies to identify protected traffic.
- **L2TP/IPsec remote access:** IPsec establishes the protected transport; L2TP establishes the PPP session inside it.

## Pre-deployment checklist

1. Confirm underlay reachability between public or transport-facing peer addresses.
2. Confirm routing design, return routes, and non-overlapping protected networks.
3. Match IKE/IPsec algorithms, authentication, lifetimes, and peer identities.
4. Account for NAT-T, firewall rules, MTU, fragmentation, and TCP MSS clamping.
5. Restrict management access and use strong, unique credentials or certificates.
6. Define monitoring, failover behavior, change window, and rollback steps.

## Verification and troubleshooting

- Check underlay reachability and route selection before troubleshooting the tunnel.
- Verify IKE negotiation, IPsec security associations, counters, and selector/proxy-ID matches.
- For GRE, verify tunnel source/destination, interface state, MTU, and routes through the tunnel.
- For L2TP, verify the control/session state, PPP authentication, assigned address, and client routes.
- Test both directions and confirm that only intended traffic is routed or selected for encryption.
- Review logs and counters at both endpoints; a tunnel being *up* does not prove application reachability.


## Reproducible lab walkthrough

- [Site-to-Site IPsec VPN with IKEv2](./ipsec-site-to-site-ikev2-lab.md) - policy-based crypto-map example, IKEv2 negotiation, ESP SAs, traffic selectors, NAT-T, verification, troubleshooting, MTU and rollback.

The walkthrough is an illustrative Cisco IOS/IOS-XE-style lab reference. It has not been claimed as validated on a named release or deployed in production. Review the exact platform syntax and cryptographic baseline before testing. Never commit real keys or production peer details.

## Lab scope

This document is a protocol and design reference. Add platform-specific lab configurations only after confirming the target vendor, model, and software release. No production deployment or physical-device validation is claimed here.

**Security:** Do not publish pre-shared keys, passwords, certificates/private keys, real peer addresses, customer networks, or unredacted configuration exports. Use documentation-only addressing in public examples.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
