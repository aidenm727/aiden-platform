# C1 Current-State and Baseline-Debt Cleanup — 2026-09-16

## Checkpoint brief

- **Why:** Represent published Workflow v1.2 truthfully and resolve the September 8 public-surface baseline debt without promoting provisional School findings.
- **Risk tier:** Tier 3; canonical current-state semantics and public evidence boundaries.
- **Exact scope:** Primary: `docs/current-state.json`, `docs/current-mission.md`, `docs/reviews/school-learning-vnext-storage-spike-evidence-2026-09-08.md`; directly related current-facing coherence edits in `README.md`, `docs/docs-map.md`, `docs/architecture/engineering-sessions.md`, and `docs/architecture/engineering-review.md`. The explicit C1 scope expansion adds `tests/test_public_surface.py` only for its phase identifier and freshness date expectations. Derived: this record, generator-owned `docs/aiden-context.md` and `docs/infrastructure-snapshot.md`, and task-owned temporary verification files under `/tmp/c1-baseline-20260916/`.
- **Exclusions:** Historical/roadmap cleanup, Atlas behavior, architecture/schema redesign, context compiler, Homelab extraction, identity migration, School runtime/storage changes, dependencies/configuration, staging, commits, refs, publication, deployment, and external writes.
- **Authority established:** The current C1 owner instruction accepts the direction and authorizes implementation/native verification. The later explicit scope expansion authorizes exactly two current-state test expectation changes and accepts provisional retention with narrow sanitization. Candidate acceptance remains pending. No publication or deployment authority exists.
- **Protected boundaries:** Preserve `Summer_2027_Internship_Review_Aiden_Menefee.md` completely. No protected refs/content, secrets, credentials, private/live School data, or live-system access. No shell network action. Generated outputs remain generator-owned.
- **Observable result:** Published W2 is the canonical repository phase; current-facing references agree; useful School evidence retains its actual provisional status; existing public-surface guardrails pass without exceptions or weakening.
- **Verification:** Native WSL Python focused public-surface, active-state, and readiness checks, followed by full native discovery, Atlas validate/missing/sync, generator reproducibility, full diff/effective-scope review, preservation checks, and fresh adversarial independent review. Existing tests use synthetic fixtures; Atlas/public-surface/generated checks explicitly inspect the current repository. Final execution and review attestations follow the frozen record in the owner-facing handoff.
- **Stop conditions:** Material architecture/schema or non-derived scope expansion; destructive action; protected/private data boundary; verification without a safe in-scope repair. No deletion is proposed.
- **Next decision boundary:** Explicit owner acceptance of the exact verified and independently reviewed uncommitted C1 candidate. No staging, commit, or push follows without separate authority.

## Baseline and preflight

Base: local `main` at `d40c2891bd5cf79f674498ac6b5fed6bb1beac47`.
Local tracking `origin/main` aligned 0/0; no fetch or remote contact occurred.
Only the internship file and September 8 report were untracked. Staged and
unstaged tracked diffs were empty. Bootstrap reported valid, synchronized,
intentionally idle published W1, exposing the stale phase C1 corrects.

Native environment: Ubuntu-22.04 WSL, Python 3.10.12, Git 2.34.1. Authorized
targets and the task temporary root were writable. No new host dependency,
service, device, or live data was required. The desktop sandbox helper failed
before command execution; approved native WSL execution supplied the environment.
The temporary root was reestablished after the usage pause. Native focused
tests started successfully before mutation. These environment events are not
product failures. No dependencies or configuration were changed.

Pre-mutation commands and observed results:

- `PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p 'test_public_surface.py'`: 19 tests, three failures.
- `PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p 'test_*.py'`: 562 tests in 64.038 seconds, three failures, one skip; exit 1.
- `PYTHONDONTWRITEBYTECODE=1 ./atlas validate`: Valid, no errors/warnings.
- `PYTHONDONTWRITEBYTECODE=1 ./atlas missing`: no missing definitions.
- `PYTHONDONTWRITEBYTECODE=1 ./atlas sync`: Synchronized, no errors/warnings.
- `git diff --check`: passed; `git status --short --branch` confirmed only the two known untracked files.

All three baseline failures concerned the September 8 report:
`test_candidate_contains_no_ip_address_literals` (line 27),
`test_legacy_repository_identity_is_confined_to_truthful_allowlist` (sole
unexpected path), and
`test_protected_historical_absolute_paths_have_narrow_dispositions` (lines 22
and 99). C1 owns this debt; no baseline exception is used for final readiness.

Pre-mutation SHA-256:

- Internship file: `d34f2f25eaf048837d2303af59f434779990e16b7d126d6b8ba4534ae1c11003`.
- September 8 report: `777bfc515c182f4ee0410d3a72a56062c1ea44a9e9736ea56ee24b6bbc857fe5`.
- Tracked tests aggregate (`git ls-files tests | xargs sha256sum | sha256sum`): `21d94d1b0708fa0b2a6aad507a58b958b55c76d7465d6be26b0c06fa79f874f0`.

## Disposition and ownership

Retain the September 8 report deliberately as provisional dated evidence.
It preserves concrete synthetic parity, identity, transaction, and recovery
findings with hashes, provenance, and explicit limitations. Inspection found
no superseding disposition. The report's final adversarial implementation
review did not complete; its architecture recommendation is not owner
acceptance. Existing `docs/architecture/school-learning.md` continues to own
the implemented filesystem/JSON storage contract. Promotion would require the
existing knowledge-promotion and owner-decision path, outside C1.

The owner explicitly accepted this retention boundary in the C1 scope
expansion. Open production prerequisites remain historical candidate findings;
C1 neither resolves nor selects that product work. The disposable prototype
was not reopened or rerun, and its present availability is not asserted.
Only public-surface locator/version details were sanitized, with an explicit
annotation identifying the equivalent repository-relative historical command.
No findings, hashes, original test outcomes, or review limitations were erased.
The original Workflow v1.1 reference remains a historical statement.

## State and coherence decisions

The current owner confirms W2 is published. Its implementation evidence exists
at base commit `d40c2891bd5cf79f674498ac6b5fed6bb1beac47`, which is also the
locally observed tracking identity. The evidence's pre-publication narrative
is preserved historically; C1 does not claim fresh remote verification or
rewrite W2 history. Phase and freshness dates are 2026-09-16. W1 and published
School operational-loop evidence remain traceable.

Canonical work selection remains intentionally idle with no future capability
checkpoint preselected, and fixed external-authority sentinels remain intact.
Current Mission distinguishes this locally authorized C1 candidate from the
published phase and from follow-on work. C1 acceptance/publication is not
inferred from W2 publication, Atlas, or idle state.

README, documentation-map navigation, and the two current session/review
version references are aligned narrowly. No architecture behavior changes.
The public-surface test originally pinned the stale phase and date. Work stopped
at that scope boundary; the owner then explicitly authorized exactly those two
assertion-value updates. No other expectation, guardrail, allowlist, or test
policy changes are permitted. Rollback is a bounded documentation restoration
under applicable authority; no runtime migration exists.

## Final verification and review boundary

This is an uncommitted candidate on the base above. The eight primary paths
listed in the brief, this record, and any changed registered generated output
form the complete candidate. `docs/infrastructure-snapshot.md` may be rewritten
by its registered generator but should retain identical bytes because its
sources did not change. The internship file remains excluded.

After this record is frozen, run the three focused discovery patterns
`test_public_surface.py`, `test_active_state.py`, and `test_atlas_readiness.py`
with `PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p PATTERN`,
then the exact full-suite command above. Run Atlas validate/missing/sync,
`git diff --check`, complete tracked/untracked candidate review and scope checks,
and preservation verification. Generate only through
`PYTHONDONTWRITEBYTECODE=1 python3 tools/generate-context.py`; confirm repeated
generation is byte-identical before the final verification sequence.

The final owner-facing handoff supplies observed closing results, candidate
hashes, and independent-review disposition without requiring another mutation
to this record. No future command result or review is claimed here. Any later
candidate mutation requires renewed final verification and applicable review.
The earlier interrupted disposition review is not a completed independent
review. A fresh adversarial reviewer must inspect the exact final C1 candidate.
Owner acceptance, staging, commit, publication, and deployment remain pending
or unauthorized as separately stated above.
