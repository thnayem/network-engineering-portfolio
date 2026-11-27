# MX204 Firewall Filters: Topology and Packet Flow

## Routing Engine protection concept

```mermaid
flowchart LR
    MGMT["Trusted management host<br/>192.0.2.128/25"] --> LO["MX204 lo0.0<br/>Routing Engine"]
    BGP["BGP peer<br/>198.51.100.2"] --> LO
    OSPF["OSPF neighbor<br/>10.0.12.0/30"] --> LO
    ICMP["Diagnostic ICMP"] --> LO
    LO --> FILTER["PROTECT-RE<br/>Input filter"]
    FILTER -->|Explicit permit| RE["Routing Engine services"]
    FILTER -->|Unmatched| DROP["Count / log / discard"]
```

## Filter term decision flow

```mermaid
flowchart TD
    A["Packet destined to lo0.0"] --> B{"SSH from trusted subnet?"}
    B -->|Yes| C["Count and accept"]
    B -->|No| D{"BGP from configured peer?"}
    D -->|Yes| E["Count and accept"]
    D -->|No| F{"OSPF from configured link?"}
    F -->|Yes| G["Count and accept"]
    F -->|No| H{"ICMP permitted?"}
    H -->|Yes| I["Count and accept"]
    H -->|No| J["Final term: count, log, discard"]
```

## Service-interface filter concept

```mermaid
flowchart TD
    A["Packet enters customer service interface"] --> B{"UDP destination port 53?"}
    B -->|Yes| C["Count DNS / accept"]
    B -->|No| D{"TCP destination port 443?"}
    D -->|Yes| E["Count HTTPS / accept"]
    D -->|No| F["Count and discard"]
```

**Critical safety note:** The lo0 attachment is commented out in the example configuration on purpose. The allow-list is not a complete management-plane service matrix. Before attaching a restrictive filter, account for every enabled service, including NETCONF, SSH, SNMP, NTP, DNS, AAA, BFD, routing protocols, monitoring, and automation. Use console/OOB access and a confirmed commit.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
