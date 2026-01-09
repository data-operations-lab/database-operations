# Backup Strategies

Backups are only useful if they can be restored.  
This document outlines practical, engine-agnostic backup strategies with an emphasis on reliability, verification, and operational discipline.

## Goals
- Protect against data loss
- Enable predictable recovery
- Minimize recovery time (RTO)
- Minimize data loss (RPO)

## Backup Types

### Logical Backups
Logical backups capture database objects (schemas, tables, rows) in a portable format.

**Advantages**
- Portable across environments
- Useful for partial restores
- Easier to inspect

**Tradeoffs**
- Slower for large datasets
- Restore time increases with size

**Operational Notes**
- Prefer consistent snapshots where available
- Always record backup duration and size
- Validate by restoring into a non-production environment

---

### Physical Backups
Physical backups capture the underlying database files.

**Advantages**
- Faster backup and restore for large systems
- Preserves internal structures
- Better suited for full system recovery

**Tradeoffs**
- Less portable
- Tied to engine version and configuration

**Operational Notes**
- Ensure filesystem consistency
- Document engine version and configuration at backup time
- Test restore procedures after version upgrades

---

## Backup Frequency
Backup frequency should align with business risk tolerance.

- Full backups on a regular schedule
- Incremental or differential backups between full runs
- Configuration and schema backups alongside data

## Retention Policy
Retention balances recovery needs and storage cost.

Consider:
- Short-term frequent backups
- Longer-term archival snapshots
- Off-site or cross-region storage

Document:
- Retention duration
- Storage location
- Deletion policy

---

## Verification and Testing

Backups that are not tested should be assumed unreliable.

**Verification Practices**
- Scheduled restore tests
- Checksum or integrity validation
- Monitoring backup job success and duration

## Failure Scenarios to Plan For
- Accidental data deletion
- Corrupted indexes or tables
- Hardware or disk failure
- Misconfigured migrations
- Partial restores under time pressure

Documenting these scenarios helps reduce recovery time during incidents.

---

## Documentation and Runbooks
Every backup strategy should have:
- Clear restore steps
- Expected recovery time
- Known limitations

Operational documentation is as important as the backup itself.

---

*This document evolves as tooling, scale, and operational requirements change.*
