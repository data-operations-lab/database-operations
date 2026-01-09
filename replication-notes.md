# Replication Notes

These notes capture operational considerations around database replication.
They focus on reliability, consistency, and failure awareness rather than specific vendor implementations.

## Why Replication Is Used
Replication is commonly introduced to:
- Improve availability
- Support read scaling
- Provide redundancy
- Reduce recovery time after failures

Replication adds resilience, but also introduces complexity that must be actively managed.

## Common Replication Models
- Primary / replica (leader / follower)
- Multi-replica topologies
- Synchronous vs asynchronous replication

Each model presents tradeoffs between consistency, latency, and failure tolerance.

## Operational Considerations
- Replication lag and its impact on reads
- Replica health and monitoring
- Failover procedures and responsibilities
- Version and schema compatibility
- Network stability and throughput

Replication should be monitored continuously, not assumed to be healthy.

## Failure Modes to Plan For
- Replica lag growing silently
- Replication breaking due to schema changes
- Split-brain scenarios
- Partial replication after outages
- Replicas falling permanently behind

Understanding these scenarios reduces recovery time during incidents.

## Migrations and Replication
Schema and data migrations must account for replication:
- Changes should be compatible across nodes
- Replication state should be validated post-migration
- Rollback plans must consider replicated data

Replication increases the importance of careful sequencing.

## Verification and Monitoring
- Track replication lag metrics
- Alert on replication errors
- Periodically validate data consistency
- Test failover and recovery procedures

## Open Questions
- What level of replication lag is acceptable?
- Which workloads are safe to read from replicas?
- How is replication health communicated during incidents?

---

*These notes evolve as replication scenarios are tested and observed in practice.*
