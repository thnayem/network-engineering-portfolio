# VPN Technologies

A protocol- and design-focused reference for virtual private networks used in enterprise and service-provider environments.

VPN is documented as a separate technical domain from tunneling. A tunnel provides encapsulation or a logical path; a VPN adds a private connectivity and security model, commonly using encryption, authentication, access control, and routing policy.

## Coverage

| VPN type | Typical use | Key design considerations |
|---|---|---|
| **Site-to-Site VPN** | Secure connectivity between offices, data centers, branches, or network sites. | Peer reachability, protected subnets, routing, redundancy, overlapping address spaces, and failover. |
| **Remote-Access VPN** | Secure user or administrator access to an organization network. | User/device authentication, MFA, address pools, split/full tunneling, endpoint posture, and least privilege. |
| **IPsec VPN** | Network-layer protection for site-to-site or remote-access connectivity. | IKEv1/IKEv2, proposals, peer identity, certificates or strong pre-shared keys, traffic selectors, NAT-T, and rekeying. |
| **Route-Based VPN** | Uses a virtual tunnel interface and routing protocols or static routes to direct traffic. | Tunnel interface state, route preference, dynamic routing, MTU/MSS, and route-leak prevention. |
| **Policy-Based VPN** | Uses security policies or traffic selectors to define which traffic is encrypted. | Selector symmetry, proxy IDs, policy ordering, subnet changes, and troubleshooting asymmetric matches. |
| **SSL/TLS VPN** | Commonly provides remote-access connectivity through a TLS-protected gateway. | TLS versions/ciphers, MFA, identity integration, client posture, portal access, and least-privilege policy. |

## Related tunnel technologies

- [GRE, IPsec, L2TP, and tunnel design notes](../tunnels/) - encapsulation, tunnel behavior, GRE over IPsec, and L2TP/IPsec.
- **GRE over IPsec** - GRE supports routing or multicast across the logical tunnel; IPsec protects the traffic between tunnel endpoints.
- **L2TP/IPsec** - L2TP carries PPP sessions while IPsec provides encryption and peer protection.

## Design checklist

1. Define the use case: site-to-site, remote access, or partner connectivity.
2. Identify protected networks, user groups, permitted services, and trust boundaries.
3. Confirm underlay reachability, routing, return paths, and non-overlapping address plans.
4. Select a supported VPN mode and align cryptographic settings at both endpoints.
5. Prefer IKEv2 where supported, modern authenticated encryption, certificates where practical, and MFA for user access.
6. Restrict access by identity, source, destination, and service. Avoid broad access to internal networks.
7. Plan redundancy, monitoring, logging, key/certificate rotation, change control, and rollback.
8. Validate MTU, fragmentation, NAT traversal, and TCP MSS where relevant.

## Verification and troubleshooting

- Confirm peer reachability and correct route selection before investigating encryption.
- Check IKE negotiation, peer identity, authentication, proposals, and security-association state.
- Verify traffic selectors or proxy IDs for policy-based VPNs.
- For route-based VPNs, inspect tunnel interface state, routing table, route preference, and return path.
- Check firewall policy, NAT exemptions, NAT-T, MTU/MSS, counters, and logs at both ends.
- Test permitted and denied traffic in both directions. A connected tunnel does not automatically mean end-to-end application access is working.

## Security and publication scope

- Use MFA for remote-access users where supported and apply least-privilege access.
- Use strong, unique secrets or certificates; rotate credentials and revoke compromised identities.
- Keep VPN gateways patched and restrict management-plane access.
- Never publish pre-shared keys, passwords, private keys, certificates, real peer addresses, customer networks, or unredacted configuration exports.

This document is a vendor-neutral design and troubleshooting reference. Platform-specific configuration examples should be added only with the target vendor, model, and software release identified. No production deployment or physical-device validation is claimed here.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
