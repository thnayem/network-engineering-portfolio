# Network Architecture Lab

**Reference date:** 2026-03-18 (archive date used for organization only)

## Logical design
```text
          [LAB-ISP-A]       [LAB-ISP-B]
               |                 |
             [EDGE-1]--------- [EDGE-2]
                  \             /
                   [CORE-L3]
                  /    |     \
             [DIST-1][DIST-2][SERVICES]
                |       |
             [ACCESS SWITCHES]
                |
             [LAB CLIENTS]
```

## Segmentation
- VLAN 10: users
- VLAN 20: voice
- VLAN 30: servers
- VLAN 99: management

## Routing
- OSPF for internal lab reachability.
- eBGP for simulated external connectivity.
- PBR only for explicitly selected test traffic.
- Prefix filters and routing policy at boundaries.

All labels and design elements are fictional. This is a learning reference, not a real company topology.
