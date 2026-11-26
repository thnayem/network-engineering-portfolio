# Access Control Lists (ACL)

**Reference date:** 2023-04-29 (archive date used for organization only)

## Objective
Control traffic between fictional lab segments using explicit, least-privilege rules.

## Cisco IOS example
```cisco
ip access-list extended LAB-USERS-TO-SERVERS
 permit tcp 192.0.2.0 0.0.0.255 203.0.113.0 0.0.0.255 eq 443
 permit udp 192.0.2.0 0.0.0.255 203.0.113.0 0.0.0.255 eq 53
 deny ip any any log
```

## Review checklist
- Confirm source, destination, protocol and port.
- Place rules in the correct direction and interface.
- Consider implicit deny behavior.
- Check rule order and counters.
- Keep management-plane access separate.
- Test permitted and denied traffic before deployment.

All addresses are documentation-only TEST-NET ranges.
