# RSTP (Rapid Spanning Tree Protocol)

**Lab date:** 2026-03-18 (reference archive date; independently authored notes)

## Design checklist
1. Select and document the intended root bridge for each spanning-tree instance.
2. Set root and secondary priorities explicitly.
3. Enable edge/PortFast behavior only on endpoint-facing ports.
4. Enable BPDU Guard on edge ports where supported.
5. Do not enable edge behavior on switch-to-switch links.
6. Verify root bridge, root ports, designated ports and topology changes.

## Cisco IOS example
```cisco
spanning-tree mode rapid-pvst
spanning-tree vlan 10,20,99 priority 4096
interface GigabitEthernet1/0/1
 spanning-tree portfast
 spanning-tree bpduguard enable
```

## Verification
```cisco
show spanning-tree summary
show spanning-tree vlan 10
show spanning-tree detail
```

Use matching vendor syntax for other switches.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
