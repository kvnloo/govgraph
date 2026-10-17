<!-- oss-factory:v1
{"id":"20261017-civic-govgraph-queue","kind":"state","project":"govgraph","from":"chatgpt","to":["factory"],"status":"working","dedupe_key":"promotion-queue:ben-kahl/govgraph","civ":{"city_id":"oss:govgraph"}}
-->

# Canonical upstream promotion queue — ben-kahl/govgraph

Tracked via registry PR https://github.com/kvnloo/oss-factory/pull/191 (provisional until merged). Fork Issues are disabled; this fork-local document is the **one canonical queue**. Original implementation PRs, issue threads, and author credit stay where they originated.

- Origin: https://github.com/ben-kahl/govgraph
- Coordination fork: https://github.com/kvnloo/govgraph
- Last evidence audit: 2026-10-17
- State: **CHECK / LOCAL_ONLY** (not origin-action authorization)

## Existing upstream review / source work

- Fork draft PR: https://github.com/kvnloo/govgraph/pull/1; **no origin PR**.
- Requirement: README promises an audit log of entity resolution; SQL table exists but resolver previously did not persist completed decisions.
- Branch: `civic/entity-resolution-audit` @ `42d12f54d772a94ab5cab8472f4070a03793635d`.
- Change: audit receipt fields, migration-safe schema, savepoint-guarded insertion when autocommit is disabled, and four mock test cases.
- Gap: full pytest + real PostgreSQL rollback/commit verification not executed; no data-pipeline benchmark. Do **not** claim production correctness.
- Next: run exact-head tests on Python 3.12/PostgreSQL; verify duplicate IDs, write costs and rollback behavior; only then consider bounded origin promotion.

## Release gates

- Record original author/reporter/maintainer provenance and exact source head SHA.
- Follow project contribution policy, current upstream reviews, conflicts, and CI checks.
- Require native targeted tests; separate static reasoning from exercised runtime evidence.
- Do not publish an overlapping origin PR or claim a fork draft is landed.
- Only a bounded human authorization under factory/HITL.md permits additional origin actions; upstream merges are for maintainers.

## Results

- **Ready for new origin publication:** none independently verified.
- **Origin writes from this coordination update:** none.
- **Next update:** when CI/reviews/test results or upstream ownership changes materially.
