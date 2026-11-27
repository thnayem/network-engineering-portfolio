# Static Routing

## Purpose

Static routes are useful for small networks, explicit service paths, stub networks, and controlled fallback routing. They should be documented with their next-hop, routing table, intended traffic, and failure behavior.

## Juniper Junos example

See [static-routing.set.example](./static-routing.set.example).

The example uses documentation-only prefixes. It includes a discard route for an aggregate and a more-specific next-hop route to illustrate longest-prefix match.

## Operational checks

```text
show route protocol static
show route 203.0.113.0/24
show route forwarding-table destination 203.0.113.10
ping 198.51.100.2
traceroute 203.0.113.10
```

Before deployment, verify next-hop reachability, route preference, recursive resolution, routing-instance scope, and a tested rollback path.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
