# School Learning vNext transactional storage and migration spike — 2026-09-08

Non-canonical, uncommitted engineering evidence. Recommendation: **ACCEPTED WITH CORRECTIONS** for the proposed SQLite plus content-addressed evidence architecture. This is a bounded synthetic feasibility result, not acceptance of a production implementation or authorization for live migration.

## Checkpoint brief

- **Why:** Reduce uncertainty about whether the proposed storage architecture preserves existing School semantics.
- **Risk tier:** Tier 3 assurance, conservatively applied to identity, migration, and recovery semantics; all executed School data is synthetic.
- **Exact scope:** Disposable code, fixtures, databases, evidence bytes, and execution outputs under `/tmp/aiden-school-vnext-storage-spike-20260908/`; this exact repository record, `docs/reviews/school-learning-vnext-storage-spike-evidence-2026-09-08.md`.
- **Exclusions:** Production storage, UI, Canvas adapters, adaptive learning, live migration, dependencies/configuration changes, Git mutations, publication, deployment, and external writes.
- **Authority established:** The current owner instruction explicitly authorizes the bounded spike and implementation. It permits a repository-required evidence record. Candidate/architecture acceptance remains an owner decision. No staging, commit, publication, or deployment authority.
- **Protected boundaries:** No live School root or Fall 2026 runtime was opened or mutated; no private course bytes or credentials were used. No protected refs were inspected. Existing code, canonical state, generated files, and unrelated paths remain unchanged.
- **Observable result:** Inspectable synthetic inputs, SQLite database/CAS output, executable probes, and this report.
- **Verification:** Current School validators, complete spike suite with adversarial/process-exit cases, canonical repository Python suite, independent semantics/storage review, and final Atlas/Git checks. Exact commands and evidence are below.
- **Stop conditions:** Expansion into live/private data, dependencies, configuration, production implementation, external actions, or unresolved repeated material failures.
- **Next decision boundary:** Owner disposition of this architecture recommendation and any separately bounded production-design checkpoint.

## 1. Exact baseline

Observed 2026-09-08 at 14:23:31 America/New_York:

- Repository: the selected local engineering checkout (absolute owner path omitted), accessed through Windows PowerShell and WSL Ubuntu-22.04.
- Branch `main`; HEAD, local `refs/heads/main`, and locally observed `refs/remotes/origin/main`: `8fef26df1ae78f8dc6751d12de9ba734d9de6fba`.
- Tracking `origin/main`; locally observed ahead/behind `0/0`; no fetch or network refresh.
- Full porcelain status, staged/unstaged name-status, and both diff checks were empty/clean.
- Atlas bootstrap: healthy within declared scope, valid, synchronized, clean; W1 published, intentional idle, no selected checkpoint. `docs/current-state.json` and Current Mission agree. The current owner request establishes this spike's authority separately.
- Ubuntu 22.04.5 LTS; Microsoft WSL2 Linux kernel version components 6 / 6 / 87 / 2; native ext4; Git 2.34.1; PowerShell 7.6.5; Python 3.10.12; linked SQLite 3.37.2, DB-API threadsafety 1.
- Disposable root created mode 0700; repository evidence directory writable. SQLite WAL, foreign keys, native imports, and rollback smoke succeeded. No added dependencies; shell network was unused.
- Initial sandbox process creation failed before execution. Approved WSL execution succeeded. An early test launcher omitted the required `tools` import path; correcting the launcher resolved that environment failure. The preliminary discovery count was not used as full-suite evidence.

Startup and authority interpretation followed `AGENTS.md`, `docs/architecture/engineering-sessions.md`, `docs/standards/engineering-collaboration.md`, `docs/architecture/repository.md`, and `docs/architecture/knowledge-authority.md`.

## 2. Prototype shape

Four disposable Python files, 924 lines total: 368-line `spike.py`, 125-line `fixture_builder.py`, and two test files. Standard-library SQLite/filesystem operations only; current School pure validators supply legacy schema/conflict validation.

SQLite has separate course/source/evidence identities, immutable source/evidence/claim versions, assessments/policies and learner records, operational observations and attempts, committed operation outcomes, a disposable derived cache, and schema migration history. Scalar payloads/envelopes retain exact legacy fields and collection ordering; this is intentionally not a fully normalized production schema.

A global application revision covers imported academic, learner, and observation state. Attempt receipts and derived-cache writes do not advance it. Version tables, observations, blob metadata, and committed outcomes reject UPDATE/DELETE. Foreign keys are enabled per connection. Storage uses WAL and synchronous=FULL on native ext4.

The CAS stores synthetic permitted bytes by SHA-256: flush a temporary file, install without overwriting an existing digest, flush the directory, then commit database references. Metadata-only migration retains declared hashes without claiming bytes are available.

`representative-input/`, `representative-output/`, and `representative-results.json` preserve one inspectable synthetic example under the disposable root. Other test databases are disposable execution evidence.

## 3. Schema and data-model findings

- Identity is independent of hash. Course keys include term/course ID; source/material IDs remain course-local. Claim keys include owner kind and owner ID because the existing claim hash excludes its owner and status.
- Free-text material/claim provenance cannot be coerced into a registered-source foreign key. Operational observations have an explicit registered-source relationship.
- Legacy observations and relationships identify mutable materials, not historical bytes. Their migrated historical-version bindings remain NULL. Initial imported versions mean “first captured by this spike,” not reconstructed historical version 1.
- Directional material/topic/assessment assertions remain separate; merging them into an undirected join would invent reciprocal facts.
- Claims retain all IDs, values, statuses, and sources. Whole-owner claim-set validation prevents a partial update from hiding an old conflict member. Supersession keeps historical rows and returns an unresolved survivor to provisional.
- Missing core/observations, absent legacy fields, explicit NULL, empty lists, unsupported scheduling prose, nullable grading strings, custom assessment types, and unknown learner state remain distinct.
- Acquisition/import attempts are operational records, separate from logical committed imports and source observations. No historical acquisition receipt is invented. Same bytes on a fresh check can produce another observation without another blob or evidence version.

These findings derive from `tools/school_learning/core.py` validators and mutation semantics, especially claim/provenance validation (1478–1554), observation references (1716–1785), directional relationships (2349–2420), and claim identity construction (2908 onward), plus `docs/architecture/school-learning.md`.

## 4. Migration/parity results

The fixture builder generated and validated registered v0.2 course-a and unregistered v0.1 course-b in synthetic-2099. It copied no live data.

Both courses round-tripped with **exact field and collection-order equality** in the retained representative result. Output: 2 courses, 2 source identities, 3 material/evidence identities sharing 1 blob, 9 assessment/policy/topic/session records, 6 claims, 2 observations, 1 logical import, and 1 actual import-attempt receipt. Revision=1, schema version=2, SQLite integrity_check=ok, foreign_key_check empty, no invalid blob references or orphans.

Covered assessments, policies, claim statuses and unresolved conflicts, free-text provenance, observations, hashes/sizes and material IDs, custom grading/type values, learner evidence, missing/unknown state, duplicate IDs in separate namespaces, and one-way relationships. A valid unsorted collection case also round-trips exactly and retries without mutation.

The importer is a versioned initial snapshot migration (`school-snapshot/v1`), not a delta merge/deletion engine. It rejects changed existing snapshots. The additive SQLite v1-to-v2 schema migration rolls back its schema/version marker on injected failure and retries successfully; unknown future formats fail closed. Semester-manifest migration, all possible real-course variants, and reconstruction of overwritten history remain outside this representative experiment.

## 5. Transaction/concurrency results

**21 spike tests passed**, including:

- Whole-command rollback after inserted rows and a foreign-key failure; no partial academic state, operation result, or revision survives.
- Same-key/same-payload replay, different-key identical snapshot no-op, and same-key/different-payload rejection.
- Two-connection stale rejection; single-writer contention reported as SQLite locking, separately from stale application revisions; stable WAL reader snapshot.
- Real child-process exit after file publication, after SQL mutation, and after commit. Pre-commit exits leave one detectable orphan and no committed references; retry reuses it. Post-commit retry returns the committed result even with the old expected revision.
- Immutable versions and a claim remaining pinned to evidence version 2 after version 3 exists.
- Fresh observations over identical bytes remain distinct; retries do not duplicate them or change learner evidence.
- Preserved conflicts, historical supersession/provisional survivor, partial-claim omission rejection, missing bytes, corrupted CAS detection, and transactional schema-upgrade failure.

Process-exit recovery is not a power-loss/fsync durability proof. The spike performs no destructive orphan collection, backup/restore, sustained throughput test, or adversarial multi-user filesystem hardening.

## 6. Corrections and architecture verdict

**ACCEPTED WITH CORRECTIONS.** No tested representational or transaction failure requires abandoning SQLite/CAS. The bare architectural proposal is insufficient if it implies a joint filesystem/database transaction or recoverable historical evidence that the legacy state never recorded.

Smallest production prerequisites:

1. Specify course/entity/claim namespaces, immutable version identities, directional relationships, and explicit unknown/availability states. Preserve legacy provenance text and unknown historical bindings.
2. Specify one command transaction/revision boundary, whole-owner conflict invariants, and durable payload-bound operation outcomes. Keep attempt recovery and fresh source observations separate from retry deduplication.
3. Specify the CAS publication/reconciliation protocol, incomplete-attempt handling, quarantine/missing-blob behavior, safe orphan-retention/collection, and a consistent database-plus-blob backup/restore contract.
4. Separate DB schema version, legacy format, importer version, and input fingerprint. Require manifest-level parity/rejection reporting, registration/semester coverage, and an explicit history-loss declaration before any live migration.
5. Pin and verify a production SQLite build and native filesystem/durability settings. The tested SQLite 3.37.2 is not a production WAL approval: official SQLite documents the WAL-reset race and fixes in 3.51.3+, or documented 3.44.6/3.50.7 backports. No dependency was changed here.

Primary SQLite references: [atomic commit](https://www.sqlite.org/atomiccommit.html), [isolation](https://www.sqlite.org/isolation.html), [constraint conflict behavior](https://www.sqlite.org/lang_conflict.html), [foreign keys](https://www.sqlite.org/foreignkeys.html), [WAL/version correction](https://www.sqlite.org/wal.html), [synchronous settings](https://www.sqlite.org/pragma.html#pragma_synchronous), and [backup API](https://www.sqlite.org/backup.html). The cross-store protocol is an engineering inference from the transaction boundary, not a SQLite guarantee.

## 7. Verification and review evidence

Completed native commands from the repository root:

    PYTHONPATH=tools:/tmp/aiden-school-vnext-storage-spike-20260908:. PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s /tmp/aiden-school-vnext-storage-spike-20260908 -p 'test_*.py' -v

Result: 21 tests, 4.629s, OK, after the last prototype/test correction.

    PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p 'test_*.py'

Result: 562 tests, 86.949s, OK (skipped=1). This is the canonical full repository command, not the preliminary discovery count.

Independent source-semantics audit found and prompted correction of unknown historical bindings and collection-order retry behavior. Independently authored parity tests passed. The separate final adversarial implementation review did not complete: its read command failed during sandbox setup and the escalated read was aborted. That reviewer inspected no prototype file and cannot attest to its invariants or hashes. Its completed official-SQLite documentation review supports the stated architectural corrections only. Accordingly this report is a provisional architecture recommendation based on observed synthetic tests and the completed semantics audit, with the final implementation-review gate outstanding; no owner acceptance is claimed.

The owner subsequently directed completion from gathered evidence without unnecessary reruns. No completed spike suite is repeated merely to write this report. Repository checks completed: `PYTHONDONTWRITEBYTECODE=1 ./atlas validate` returned Valid with no errors/warnings; `PYTHONDONTWRITEBYTECODE=1 ./atlas missing` reported all discovered definitions present; `PYTHONDONTWRITEBYTECODE=1 ./atlas sync` returned Synchronized with zero errors/warnings. The complete new-file diff was inspected. Its sole whitespace finding (a trailing blank line from transport) was corrected. HEAD remains the baseline and the only repository change is this untracked report. Final whitespace/status confirmation accompanies the handoff.

Artifact SHA-256 identities:

| File under disposable root | SHA-256 |
|---|---|
| spike.py | aa438c13cb4cecf1249250951c29192d02ba74eb4685e4ff39afcf88dc470a20 |
| fixture_builder.py | f7d4e4aa09de70d8de1c8b80272b5846915029c1f249b3b78b16bd0a8d6be9a5 |
| test_spike.py | 9bd41c1de759f5488965aba13a5e2e8155b1f96bf9b9e2fce5300b8f875b00f6 |
| test_failures.py | bac9df01fb137d6492c918c06a3704385f5f1b3970d9ccc11ad0b644acb7a7f0 |

## 8. Lifecycle and retained boundary

The spike is an uncommitted evidence candidate; architecture/candidate acceptance remains with the owner. Only this dated report is retained inside the repository because Workflow v1.1 requires one ordinary Tier 2/3 evidence record. The prototype and all School data remain disposable outside the repository. No production/runtime file, generated artifact, canonical active state, branch, ref, dependency, or external system was changed. No live-data smoke or migration is claimed.

## C1 public-surface disposition — 2026-09-16

Retained by explicit owner direction as provisional dated synthetic evidence.
This disposition does not accept the proposed architecture, complete the
unfinished independent review, promote findings into School architecture, or
authorize production work. The existing School architecture remains the owner
of the implemented storage contract.

Only public-surface details were sanitized: the absolute checkout locator and
its legacy slug were omitted, the WSL kernel version was expressed as
components, and the device locator was omitted. In the historical test command,
`.` represents the repository root instead of its absolute owner path; the
command was originally run from that root. No spike command was rerun in C1.
Findings, limitations, artifact hashes, and the original review status remain
as recorded; availability of the disposable prototype was not reverified.
