# Cisco 7606-S: Verification and Rollback

## Before lab deployment
1. Confirm exact chassis, supervisor engine, line cards, IOS image and licenses.
2. Check command support and hardware forwarding restrictions.
3. Confirm out-of-band console access and a saved configuration.
4. Validate both ends of EtherChannel and VLAN tagging.
5. Check VRF route isolation and PBR return routing.
6. Never paste the integrated file into a production router.

## Suggested verification commands

### Platform and interfaces
    show version
    show inventory
    show module
    show ip interface brief
    show interfaces status
    show etherchannel summary
    show interfaces port-channel 5

### VLAN and spanning tree
    show vlan brief
    show spanning-tree summary
    show spanning-tree vlan 30

### VRF and routing
    show ip vrf
    show ip route vrf INTERNET
    show ip route vrf CDN
    show ip route vrf CACHE
    show ip ospf neighbor
    show ip ospf vrf INTERNET

### BGP and policy
    show ip bgp vpnv4 all summary
    show ip bgp vpnv4 vrf INTERNET summary
    show ip bgp vpnv4 vrf CDN summary
    show route-map
    show ip prefix-list

### PBR and QoS
    show ip policy
    show route-map CACHE-PBR
    show policy-map interface Port-channel5.300

### Monitoring
    show ip cache flow
    show monitor session

Some commands differ across IOS releases and feature sets; use platform CLI help and command reference.

## Change safety
- Save a known-good configuration and capture current state.
- Use console/OOB access.
- Apply one feature segment at a time.
- Validate syntax and platform support before applying.
- Confirm management, routing and traffic behavior after each change.
- Roll back the last change from the saved configuration if reachability or forwarding is affected.

---

**A note on this documentation:** The technical work and experience behind these notes are mine. Some wording and the way I have organized the material have had AI assistance, mainly to make the writing clearer and save time. The examples, decisions and work described are not AI-generated. I check what I publish and stand behind it.
