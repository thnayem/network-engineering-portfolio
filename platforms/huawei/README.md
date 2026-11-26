# Huawei VRP Lab

**Reference archive date:** 2023-04-29  
**Platform:** Huawei VRP-style switching (illustrative)

> Newly authored fictional lab content. No original OLT, customer, or production switch configuration is included.

## VLAN and access/trunk ports
```text
system-view
vlan batch 10 20 99
interface GigabitEthernet0/0/1
 port link-type access
 port default vlan 10
 quit
interface GigabitEthernet0/0/48
 port link-type trunk
 port trunk allow-pass vlan 10 20 99
 quit
```

## Verification
```text
display vlan
display interface brief
display current-configuration interface GigabitEthernet0/0/48
```

Command availability and interface numbering vary by VRP platform and release. Test in a lab before use.
