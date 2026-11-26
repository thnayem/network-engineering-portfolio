# Cisco Nexus NX-OS Lab

**Reference archive date:** 2023-04-29  
**Platform:** NX-OS-style switching (illustrative)

> Independently authored fictional lab. No original switch export or topology is reproduced.

## VLAN and trunk
```text
feature interface-vlan
vlan 10
  name USERS
vlan 20
  name VOICE
vlan 99
  name MANAGEMENT

interface Ethernet1/1
  description LAB-ACCESS
  switchport
  switchport mode access
  switchport access vlan 10

interface Ethernet1/48
  description LAB-UPLINK
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 10,20,99
```

## Verification
```text
show vlan brief
show interface trunk
show spanning-tree
show interface status
```

Validate feature availability and exact syntax on the target Nexus model and NX-OS release.
