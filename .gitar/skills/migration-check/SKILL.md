---
name: migration-check
description: Check a PR's database migrations against the Concord Voice migration rules
---

For each new or changed file under a `migrations/` directory:
1. Name is `NNNNNN_name.up.sql` with a matching `.down.sql`, numbered one past the highest on the base branch with no gap or clash.
2. No `DROP TABLE` or `DROP COLUMN` without a data migration. `NOT NULL` additions have a `DEFAULT`. Timestamps are `TIMESTAMPTZ`.
3. A file with more than one statement does not use `CREATE INDEX CONCURRENTLY`.
4. Encrypted columns are `BYTEA`. No plaintext secrets. RBAC changes need security review.
5. The down migration reverses the up migration.

Report each file as pass or fail with the line and the rule.
