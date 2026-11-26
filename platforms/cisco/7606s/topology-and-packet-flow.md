# Cisco 7606-S: Topology and Packet Flow

The diagrams below show the logical relationships used in this example. Names and addresses are fictional and do not identify a live network.

## Logical topology

```mermaid
flowchart TB
    UP["Upstream Network<br/>Documentation Peer"] <-->|"Routed service handoff"| CORE["Cisco 7606-S Core<br/>Multi-VRF BGP"]
    CDN["Service Network<br/>Documentation Peer"] <-->|"802.1Q service handoff"| CORE
    CORE <-->|"802.1Q trunk / static EtherChannel<br/>Port-channel5 · mode on"| DIST["Distribution Switch"]
    DIST --> CACHE["Service VLAN<br/>Documentation subnet"]
    DIST --> MGMT["Management VLAN<br/>Documentation subnet"]
    CORE --- VRF1["Service VRF A"]
    CORE --- VRF2["Service VRF B"]
    CORE --- VRF3["Service VRF C"]
    CORE --- VRF4["Management VRF"]
```

## BGP route-policy flow

```mermaid
flowchart TD
    A["Route received from peer"] --> B{"Which VRF peer?"}
    B -->|Service A| C["Inbound route-map"]
    B -->|Service B| D["Inbound route-map"]
    C --> E{"Matches permitted prefix policy?"}
    D --> E
    E -->|No| X["Reject"]
    E -->|Yes| F["Apply route attributes"]
    F --> G["Install eligible route in that VRF"]
    G --> H["Outbound route-map checks approved prefixes"]
    H --> I["Advertise only permitted routes"]
```

## PBR forwarding flow

```mermaid
flowchart TD
    A["Packet enters selected interface"] --> B{"Matches source ACL?"}
    B -->|No| C["Normal routing lookup"]
    B -->|Yes| D["Apply route-map policy"]
    D --> E["Select policy-directed forwarding path"]
    E --> F{"Valid route and return path?"}
    F -->|Yes| G["Forward"]
    F -->|No| H["Investigate route resolution / asymmetric path"]
```

## Layer 2 aggregation

The configuration example uses static EtherChannel with `channel-group 5 mode on`. It does not negotiate LACP. Both ends of the bundle must be configured consistently, including member interfaces and trunk settings.

The switching example documents PVST. It does not claim to demonstrate Rapid-PVST+.
