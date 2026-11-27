# MX204 PBR: Topology and Packet Flow

## Logical topology

```mermaid
flowchart LR
    H["Lab Client<br/>10.10.10.10/24"] --> LAN["MX204 et-0/0/3.0<br/>10.10.10.1/24"]
    LAN --> F["LAN-PBR<br/>Ingress filter"]
    F -->|Source 10.10.10.0/24| RI["PBR-ISP2<br/>Forwarding table"]
    RI --> WAN["et-0/0/4.0<br/>198.51.100.9/30"]
    WAN --> NH["Lab next-hop<br/>198.51.100.10"]
    F -->|Other traffic| RT["Master routing table"]
    F -->|Private / bypass destinations| RT
```

## Packet decision flow

```mermaid
flowchart TD
    A["Packet enters LAN interface"] --> B{"Destination in bypass prefix?"}
    B -->|Yes| C["Accept: normal routing"]
    B -->|No| D{"Source in 10.10.10.0/24?"}
    D -->|Yes| E["Increment PBR counter"]
    E --> F["Select PBR-ISP2 forwarding table"]
    F --> G["Resolve next-hop 198.51.100.10"]
    D -->|No| H["Accept: normal routing"]
```

## Reading the diagram
1. Traffic enters the MX204 from the lab LAN.
2. The filter checks bypass destinations first.
3. Matching source traffic is directed to the PBR forwarding table.
4. Unmatched traffic follows the master routing table.

**Important:** Confirm route resolution, return routing, filter direction, and Junos forwarding-instance support in the target lab. Addresses are documentation values.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
