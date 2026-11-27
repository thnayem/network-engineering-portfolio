# MX204 Logical Systems: Topology and Route Flow

## Master and CDN-LS logical topology

```mermaid
flowchart TB
    subgraph MASTER["Master routing context · AS 65010"]
      MLO["lo0.0<br/>192.0.2.1/32"]
      MLT["lt-0/0/0.500<br/>10.255.0.1/30"]
      MLO --- MLT
    end
    subgraph CDN["Logical system CDN-LS · AS 65010"]
      CLO["lo0.20<br/>192.0.2.20/32"]
      CLT["lt-0/0/0.501<br/>10.255.0.2/30"]
      AE["ae0.100 / ae0.200<br/>VLAN handoffs"]
      CLO --- CLT
      CLO --- AE
    end
    MLT <-->|"Logical tunnel pair<br/>iBGP over loopbacks"| CLT
```

## Route exchange concept

```mermaid
flowchart TD
    A["Master context"] --> B["Static route to CDN-LS loopback<br/>via 10.255.0.2"]
    C["CDN-LS context"] --> D["Static route to master loopback<br/>via 10.255.0.1"]
    B --> E["Loopback reachability"]
    D --> E
    E --> F["iBGP session between<br/>192.0.2.1 and 192.0.2.20"]
    F --> G["Exchange routes subject to policy"]
    G --> H["Separate routing tables per context"]
```

The paired logical-tunnel units provide an internal routed connection between the master and CDN-LS contexts. Each context has its own loopback and routing process. The same AS on both sides makes the BGP session iBGP.

The ae0 VLAN units are service handoffs inside CDN-LS. Confirm physical interface ownership, aggregate configuration, encapsulation, and logical-system feature support for the exact MX204/Junos release.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
