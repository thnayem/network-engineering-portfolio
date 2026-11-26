# Routing Policy

**Lab date:** 2026-03-18 (reference archive date; independently authored notes)

## Policy checklist
- Define exact permitted prefixes.
- Set explicit default reject behavior where appropriate.
- Apply inbound policy to external peers.
- Apply outbound policy before route advertisement.
- Set local preference, MED, communities or route tags only where required.
- Use prefix limits and review policy counters.
- Document policy intent and expected route table changes.

## Example prefix list (Cisco IOS)
```cisco
ip prefix-list LAB-OUT seq 10 permit 192.0.2.0/24
ip prefix-list LAB-OUT seq 100 deny 0.0.0.0/0 le 32
```

This is a small teaching example, not a complete internet routing policy. Review exact-match and length-match behavior before use.
