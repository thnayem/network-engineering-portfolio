# Network Troubleshooting Runbook

## Method

Use a repeatable, evidence-based sequence. Avoid changing multiple variables at once.

### 1. Define the symptom
- What is unavailable?
- Which users, VLANs, sites, or services are affected?
- When did it start?
- Is the impact total, intermittent, or performance-related?

### 2. Establish the physical layer
- Check power, link state, optics, fiber, patching, and interface errors.
- Compare both ends of the link.
- Confirm speed, duplex, transceiver compatibility, and light levels where applicable.

### 3. Check Layer 2
- Verify VLAN membership, access/trunk mode, allowed VLANs, native VLAN, MAC learning, and STP state.
- Check for loops, err-disable, port-security, and interface flaps.

### 4. Check Layer 3
- Verify interface addressing, VRF/routing-instance, ARP/ND, route lookup, next-hop reachability, and routing adjacency.
- Check route policy, prefix filters, PBR, and asymmetric paths.

### 5. Check services and policy
- Review ACL/firewall counters, NAT, QoS/policers, DNS, DHCP, and application ports.
- Test from both the client and the network edge where possible.

### 6. Change safely
- Capture the current state.
- State the expected result and rollback command before making a change.
- Make one change at a time.
- Verify service restoration and monitor for recurrence.

## Evidence template

| Field | Record |
|---|---|
| Start time and timezone | |
| Affected site/service | |
| Scope and user impact | |
| Last known good state | |
| Physical/L2/L3 findings | |
| Tests and command output | |
| Change made | |
| Verification result | |
| Rollback performed or available | |
| Follow-up action | |

Do not publish customer identifiers, live IP inventories, credentials, private logs, or unredacted screenshots.
