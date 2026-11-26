# MikroTik RouterOS Lab

**Reference archive date:** 2026-03-18  
**Platform:** MikroTik RouterOS v7

> Practical configuration demonstration using fictional names, addresses, VLAN IDs, and ASNs. This is a purpose-built example, not a raw device export.

## VLAN-aware bridge

```routeros
/interface bridge
add name=br-lab vlan-filtering=no protocol-mode=rstp
/interface bridge port
add bridge=br-lab interface=ether2 pvid=10
add bridge=br-lab interface=ether3 pvid=20
add bridge=br-lab interface=ether4
/interface bridge vlan
add bridge=br-lab vlan-ids=10 tagged=br-lab,ether4 untagged=ether2
add bridge=br-lab vlan-ids=20 tagged=br-lab,ether4 untagged=ether3
add bridge=br-lab vlan-ids=99 tagged=br-lab,ether4
/interface bridge
set br-lab vlan-filtering=yes
```

## Routed transit VLAN and OSPF

The router's bridge CPU port and the trunk carry VLAN 99 tagged. The /30 address and OSPF interface template use the same subnet.

```routeros
/interface vlan
add name=vlan99-transit interface=br-lab vlan-id=99
/ip address
add address=192.0.2.1/30 interface=vlan99-transit comment=LAB-TRANSIT
/routing ospf instance
add name=lab-v2 version=2 router-id=10.255.0.1
/routing ospf area
add name=backbone instance=lab-v2 area-id=0.0.0.0
/routing ospf interface-template
add area=backbone networks=192.0.2.0/30
```

## Verification

```routeros
/interface bridge vlan print
/interface bridge port print
/interface vlan print
/ip address print
/routing ospf neighbor print
/routing route print
```

Check RouterOS syntax against the exact target release and test VLAN forwarding and OSPF adjacency in CHR or an isolated lab before operational use.
