# MX204 Firewall Filters: Verification and Rollback

## Before attaching
    show configuration interfaces lo0 | display set
    show configuration system services | display set
    show configuration protocols | display set
    show | compare
    commit check

The lo0 attachment is commented. Do not enable it until every required control-plane service has an explicit tested permit.

## Verify
    show firewall
    show firewall filter PROTECT-RE
    show firewall filter CUSTOMER-EDGE-IN
    show configuration firewall | display set
    show interfaces lo0 extensive

Test SSH, routing adjacencies, monitoring, and required services from independent sessions. Confirm expected counters increment.

## Safe commit
    commit confirmed 5
After all checks pass:
    commit

## Rollback
    configure
    rollback 1
    show | compare
    commit check
    commit confirmed 5

If remote access is lost, let confirmed commit expire or use console/OOB recovery. Never rely solely on an in-band session when changing lo0 filters.
