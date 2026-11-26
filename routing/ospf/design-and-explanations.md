# MX204 OSPF: Design and Explanation

## Objective
Form an OSPF adjacency in backbone area 0 between MX204 and a lab core router.

## Address plan
| Interface | Address | Purpose |
|---|---|---|
| MX204 lo0.0 | 192.0.2.1/32 | Stable router ID / advertised loopback |
| MX204 et-0/0/5.0 | 10.0.12.1/30 | P2P link |
| LAB-CORE link | 10.0.12.2/30 | Neighbor |
| LAB-CORE loopback | 192.0.2.2/32 | Remote test prefix |

## Explanation
- router-id should be unique and stable.
- lo0.0 is passive: its prefix is advertised without sending hello packets.
- et-0/0/5.0 forms a point-to-point adjacency in area 0.
- Hello/dead timers are explicitly 10/40 seconds; the neighbor must match.
- The remote router must advertise its loopback for the MX204 to learn 192.0.2.2/32.

## Production notes
Use passive interfaces by default and enable adjacency only on intended links. Plan authentication, unique router IDs, route redistribution policy, BFD support/timers, and monitoring. Do not redistribute static or BGP routes without explicit policy.
