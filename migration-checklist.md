# Migration Checklist

Database migrations introduce risk and should be approached with deliberate planning and verification.
This checklist captures operational considerations intended to reduce unexpected failures.

## Pre-Migration
- Identify source and target versions
- Validate backup availability and restore paths
- Review schema compatibility
- Identify large or high-risk tables
- Confirm replication or downstream dependencies
- Establish rollback criteria

## Testing
- Test migrations in a non-production environment
- Validate application behavior post-migration
- Compare row counts and checksums where feasible
- Measure migration duration and performance impact

## Migration Execution
- Schedule during a defined maintenance window
- Monitor logs and system metrics
- Record start and end times
- Capture any deviations from the plan

## Post-Migration Verification
- Validate data integrity
- Confirm replication or downstream consumers
- Monitor performance and error rates
- Document lessons learned

## Rollback Considerations
- Define clear rollback triggers
- Confirm rollback procedure is tested
- Ensure backups are retained until stability is confirmed

---

*This checklist evolves as new migration scenarios are encountered.*
