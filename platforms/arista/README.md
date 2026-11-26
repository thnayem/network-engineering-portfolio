# Arista EOS Lab

**Reference archive date:** 2023-04-29  
**Platform:** Arista EOS-style switching (illustrative)

> Independently authored fictional lab notes. No original switch configuration is included.

## VLAN and trunk example
```text
vlan 10
   name USERS
vlan 20
   name VOICE
!
interface Ethernet1
   description LAB-USER-PORT
   switchport mode access
   switchport access vlan 10
!
interface Ethernet48
   description LAB-UPLINK
   switchport mode trunk
   switchport trunk allowed vlan 10,20,99
```

## Verification
```text
show vlan
show interfaces trunk
show spanning-tree
show interfaces status
```

Confirm syntax against the exact EOS release and hardware platform before use.
