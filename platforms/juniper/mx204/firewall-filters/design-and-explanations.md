# MX204 Firewall Filters: Design and Explanation

## Stateless filtering
Junos firewall filters match packet fields such as source/destination, protocol, and port. They are stateless and do not automatically create connection state.

## Routing-engine protection
PROTECT-RE is intended for lo0.0 input. It permits SSH from 192.0.2.128/25, BGP from 198.51.100.2, OSPF from 10.0.12.0/30, and ICMP diagnostics. The final term counts, logs, and discards unmatched traffic.

This is not a complete management policy. Add only required services and trusted source prefixes. If NETCONF, SNMP, NTP, DNS, TACACS/RADIUS, BFD, or other control-plane services are enabled, explicitly account for them before attaching the filter.

## Term order
Terms are evaluated in order. Specific permits must precede the final deny. A broad deny placed too early can block required traffic.

## Service filter
CUSTOMER-EDGE-IN permits DNS over UDP and HTTPS over TCP, then discards unmatched traffic. This is a minimal illustration, not a general customer policy. Real DNS use may require TCP as well as UDP and should be explicitly designed.

## Counters and logging
Counters help confirm matching. Logging every dropped packet can increase control-plane load. Evaluate rate limiting and platform behavior before using at scale.

## Safety
A restrictive lo0 filter can break remote management, routing, monitoring, and automation. The attachment line is commented deliberately. Use console/OOB, confirmed commit, and a complete service matrix.
