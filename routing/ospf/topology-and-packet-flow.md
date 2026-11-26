# MX204 OSPF: Topology and Packet Flow

## Area 0 topology

```mermaid
flowchart LR
    MX["MX204<br/>RID 192.0.2.1<br/>lo0 192.0.2.1/32"] ---|"Area 0<br/>10.0.12.1/30 ↔ 10.0.12.2/30"| CORE["LAB-CORE<br/>RID 192.0.2.2<br/>lo0 192.0.2.2/32"]
    MX -. "Passive loopback advertisement" .-> LSDB["OSPF Area 0 LSDB"]
    CORE -. "Advertises loopback" .-> LSDB
```

## OSPF control-plane flow

```mermaid
flowchart TD
    A["Link up"] --> B["OSPF Hello packets"]
    B --> C{"Area, timers, network type<br/>and authentication match?"}
    C -->|No| D["No Full adjacency<br/>check interface and logs"]
    C -->|Yes| E["Neighbor state progresses"]
    E --> F["Database Description exchange"]
    F --> G["LSR / LSU / LSA exchange"]
    G --> H["Synchronized LSDB"]
    H --> I["SPF calculation"]
    I --> J["Install eligible OSPF routes"]
```

The MX204 loopback is passive: its prefix is advertised but it does not form an adjacency. The routed link forms the adjacency. The remote router must advertise 192.0.2.2/32 for the MX204 to learn it.

Both ends must agree on area, timers, network type, and authentication. This diagram describes OSPF control-plane behavior, not user-packet forwarding.
