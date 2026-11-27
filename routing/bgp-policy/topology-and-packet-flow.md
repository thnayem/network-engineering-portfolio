# MX204 BGP Policy: Topology and Route Flow

## eBGP lab topology

```mermaid
flowchart LR
    TRANSIT["LAB-TRANSIT<br/>AS 65030<br/>198.51.100.2"] <-->|"eBGP / TCP 179"| MX["MX204<br/>AS 65010"]
    MX --> RIB["Local routing table"]
    OWN["Authorized lab prefix<br/>203.0.113.0/24"] --> RIB
```

## Inbound policy flow

```mermaid
flowchart TD
    A["Route received from eBGP peer"] --> B["TRANSIT-IN"]
    B --> C{"Prefix in approved inbound list?"}
    C -->|No| X["Reject route"]
    C -->|Yes| D["Set local preference 180"]
    D --> E["Accept into BGP"]
    E --> F["Best-path selection"]
```

## Outbound policy flow

```mermaid
flowchart TD
    A["Candidate route in local RIB"] --> B["TRANSIT-OUT"]
    B --> C{"Prefix is 203.0.113.0/24?"}
    C -->|No| X["Reject / do not advertise"]
    C -->|Yes| D["Add community 65010:100"]
    D --> E["Accept for advertisement"]
    E --> F["Advertise to eBGP peer"]
```

The alternate prepend policy adds the local AS twice before export. It is defined separately and is not active by default. A remote network may still choose another path based on its own policy.

This is a route-policy diagram. Ensure peer link addressing and peer-side configuration are consistent in a complete two-router lab. ASNs and prefixes are fictional.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
