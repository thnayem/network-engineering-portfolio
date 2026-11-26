# BGP Lab

**Lab date:** 2026-03-18 (reference archive date; independently authored example)

## Fictional topology
- AS 64520: local lab
- AS 64521: external lab peer
- Peering link: 192.0.2.4/30
- Peer address: 192.0.2.6

## Cisco IOS
```cisco
router bgp 64520
 bgp log-neighbor-changes
 neighbor 192.0.2.6 remote-as 64521
 address-family ipv4
  neighbor 192.0.2.6 activate
 exit-address-family
```

## Junos
```junos
set routing-options autonomous-system 64520
set protocols bgp group LAB-EBGP type external
set protocols bgp group LAB-EBGP peer-as 64521
set protocols bgp group LAB-EBGP neighbor 192.0.2.6
```

## Operational safeguards
- Apply explicit import and export policies.
- Use prefix limits where supported.
- Filter bogons and unexpected route ranges.
- Protect the control plane and restrict peer reachability.
- Never copy a live peer address, ASN, password or route policy into this lab.

## Verification
`show bgp summary`, `show ip bgp summary`, `show route protocol bgp`.
