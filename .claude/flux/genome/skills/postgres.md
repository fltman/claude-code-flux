---
skill: postgres
type: domain
default-weight: 0.6

provides-tools: [Read, Write, Bash]
synergizes-with: [analytical, methodical, defensive]

contextual-value:
  security-critical:
    value: BENEFICIAL
    historical-fitness: +22%
    recommendation: Proper data handling critical
  
  performance:
    value: ESSENTIAL
    historical-fitness: +35%
    recommendation: Query optimization crucial
  
  general:
    value: BENEFICIAL
    historical-fitness: +15%
    recommendation: Include for data-heavy work
---

# PostgreSQL Skill

## Capability Injection

```
You have deep PostgreSQL expertise:

SCHEMA DESIGN
- Normalize to 3NF by default
- Denormalize deliberately for performance (with justification)
- Use appropriate types (don't store numbers as text!)
- Foreign keys for referential integrity
- Consider query patterns when designing

QUERIES
- EXPLAIN ANALYZE before optimizing
- Index columns in WHERE, JOIN, ORDER BY
- Avoid SELECT * in production
- Use CTEs for readability
- Prefer set operations over loops/cursors

INDEXING
- B-tree for equality and range (default)
- GIN for full-text search, JSONB, arrays
- Partial indexes for filtered queries
- Don't over-index - writes suffer
- Monitor unused indexes

MIGRATIONS
- One change per migration
- Must be reversible (up AND down)
- Test on production-like data
- Consider lock implications
- Version control everything

SAFETY
- Transactions for multi-step operations
- Appropriate isolation level (read committed usually)
- Parameterized queries ALWAYS (SQL injection)
- Backup before schema changes
- Connection pooling (pgbouncer)

PERFORMANCE
- VACUUM and ANALYZE regularly
- Partition large tables
- Connection pooling
- Tune work_mem, shared_buffers
- Monitor slow query log
```

## Contextual Value

### performance: ESSENTIAL
+35% fitness. Database is often the bottleneck.

### security-critical: BENEFICIAL
+22% fitness. Proper data handling, no SQL injection.

## Synergies

- **+ analytical:** Optimized query design
- **+ methodical:** Consistent migration practices
- **+ defensive:** Safe transaction handling
- **+ cautious:** Backup before migrate

## Gaming Detection

Poor database work indicators:
- N+1 queries present → -15 fitness
- Missing indexes on hot paths → -10 fitness
- Unsafe migrations (no rollback) → -20 fitness
- Raw string concatenation in queries → -50 fitness (SQL injection!)

## Tools Granted

Read, Write, Bash (psql, migrations)

## Self-Modification Triggers

REDUCE when: No database work, frontend-only
INCREASE when: Data-heavy features, performance optimization, security context
