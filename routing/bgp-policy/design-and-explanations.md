# MX204 BGP Policy: Design and Explanation

## Prefix allow-lists
LAB-ACCEPTED-INBOUND defines the inbound route this lab accepts. TRANSIT-IN rejects everything else. In production, use peer-authorized prefixes and decide explicitly whether more-specific routes are allowed.

## Local preference
The accepted route receives local preference 180. Higher local preference is generally preferred within the local AS; it is not propagated to ordinary eBGP peers.

## Export control
TRANSIT-OUT advertises only 203.0.113.0/24 from the own-prefix list, adds community 65010:100, and rejects all other routes. The route must exist in the local routing table to be eligible for advertisement.

## Communities
A community is a tag that can influence policy on routers that recognize it. Never assume a provider community has a meaning unless it is documented and agreed.

## AS-path prepend
TRANSIT-OUT-PREPEND adds the local AS twice to the AS path. This may make the path less attractive to some remote networks, but remote local preference and other policy can override it. The prepend policy is defined but not active by default.

## Hardening
Consider maximum-prefix limits, RPKI origin validation, AS-path/bogon filters, route authorization, IPv6 policy, and monitoring.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
