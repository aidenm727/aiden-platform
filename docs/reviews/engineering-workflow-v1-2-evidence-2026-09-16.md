# Engineering Workflow v1.2 — W2 Evidence — 2026-09-16

## Checkpoint brief

- **Why:** Reduce mechanical permission friction while preserving consequential
  human decisions and truthful verification.
- **Risk tier:** Tier 3; repository authority and broad engineering contracts.
- **Exact scope:** Primary: `AGENTS.md`,
  `docs/standards/engineering-collaboration.md`, and
  `docs/architecture/engineering-lifecycle.md`. Derived: this dated evidence
  record and task-owned temporary verification logs under
  `/tmp/w2-workflow-CYw3j7`. No registered generated output consumes these
  sources, so no generated changes are required.
- **Exclusions:** Atlas, schemas, context compiler, runtime/tooling, tests and
  policy outside the named contracts, dependencies/configuration, unrelated
  owner files, broad cleanup, Homelab extraction, and identity changes.
- **Authority established:** The current owner's W2 instruction explicitly
  accepts the six-part design and authorizes bounded implementation and native
  verification, including this evidence record. Candidate acceptance is
  pending. Staging, commit, push, publication, deployment, external writes,
  and secret/protected-content access are not authorized.
- **Protected boundaries:** No secret, private-data, credential, protected-ref,
  or live-system access. Preserve unrelated owner files and existing test rules.
  Generated files remain generator-owned. No network action is authorized.
- **Observable result:** Three coherent contracts distinguish primary/derived
  scope, baseline debt, automatic bounded correction, consequential stops,
  meaningful human gates, conditional local commit authority, and compact
  task handoffs.
- **Verification:** Native Ubuntu WSL Python, existing dependencies, isolated
  synthetic fixtures in existing tests, and an explicitly identified current-
  repository smoke boundary for Atlas/public-surface/generated checks. Focused
  public-surface, active-state, and Atlas-readiness tests precede the full native
  suite. Final Atlas validate/missing/sync, complete diff/path review, preservation
  hashes, and fresh adversarial independent review follow the last mutation.
- **Stop conditions:** Material accepted-architecture change, non-derived
  canonical expansion, risk/protected-boundary change, dependency/configuration/
  runtime change, required external action, material contract conflict, or
  verification without a safe in-scope repair.
- **Next decision boundary:** Explicit owner acceptance of the exact verified
  and independently reviewed uncommitted candidate.

## Preflight and baseline

Base: `main` at `3fe854c964043343d43214821d732cb18bf370c7`.
Local tracking observation: `origin/main`, no local ahead/behind difference;
no fetch or remote contact. Canonical state remains intentionally idle at
published W1. It is not rewritten to select or grant W2 authority; the current
owner instruction supplies W2's authority.

Repository startup and checks:

- `PYTHONDONTWRITEBYTECODE=1 ./atlas bootstrap`: valid, synchronized, dirty
  only from the two owner files below; Atlas establishes no authority.
- `git branch --show-current`, `git rev-parse HEAD`,
  `git status --short --branch`,
  `git status --porcelain=v1 --untracked-files=all`, and
  `git for-each-ref --format="%(refname:short) %(objectname) %(upstream:short) %(upstream:track)" refs/heads/main`:
  observations above.
- `git diff --name-status`, `git diff --cached --name-status`, and
  `git diff --check`: no tracked baseline changes or whitespace errors.
- `PYTHONDONTWRITEBYTECODE=1 ./atlas validate`: valid, no errors/warnings.
- `PYTHONDONTWRITEBYTECODE=1 ./atlas missing`: no missing definitions.
- `PYTHONDONTWRITEBYTECODE=1 ./atlas sync`: synchronized, zero errors/warnings.

Native environment: Python 3.10.12, Git 2.34.1, Ubuntu-22.04 on WSL2.
The repository root was resolved and authorized files/directories were writable.
A task-specific writable temporary directory was created as named above.
Existing focused tests successfully started before mutation. No device/service,
additional dependency, configuration change, or network access was required.
The Windows sandbox execution helper failed before execution; approved WSL
commands supplied the accepted native environment. That environment failure
is distinct from the executed baseline assertion failures. Unavailable `rg`
was replaced by existing local search tools without installation.

Unrelated owner files were untracked and are excluded. SHA-256 baseline:

- `Summer_2027_Internship_Review_Aiden_Menefee.md`:
  `d34f2f25eaf048837d2303af59f434779990e16b7d126d6b8ba4534ae1c11003`.
- `docs/reviews/school-learning-vnext-storage-spike-evidence-2026-09-08.md`:
  `777bfc515c182f4ee0410d3a72a56062c1ea44a9e9736ea56ee24b6bbc857fe5`.
- Tracked test-file aggregate using
  `git ls-files tests | xargs sha256sum | sha256sum`:
  `21d94d1b0708fa0b2a6aad507a58b958b55c76d7465d6be26b0c06fa79f874f0`.

### Approved baseline debt

Before mutations,
`PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p 'test_public_surface.py'`
ran 19 tests with three failures.
`PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p 'test_*.py'`
ran 562 tests with the same three failures and one skip (88.173 seconds).
These are failing suite results, not passing verification.

All three failures concern only the excluded September 8 evidence file:

1. `test_candidate_contains_no_ip_address_literals`: finding at line 27.
2. `test_legacy_repository_identity_is_confined_to_truthful_allowlist`:
   that file is the sole unexpected path after the test's self exclusion.
3. `test_protected_historical_absolute_paths_have_narrow_dispositions`:
   findings at lines 22 and 99.

The current owner explicitly approves this exact unchanged baseline for W2.
The baseline was reproduced before edits; no failure was repaired, filtered,
concealed, or absorbed into scope. Protected-looking literals are not copied
into this public evidence. Final comparison must check failure identities,
paths/lines, file hashes, and unchanged test rules, not merely counts.

## Design and risk disposition

- Primary scope remains explicitly owner-authorized. Derived scope is limited
  to required evidence, registered generation, and task-owned temporary
  fixtures, with path disclosure before writing and owner exclusions controlling.
- Baseline debt cannot justify passing claims or suppress regressions. Missing
  or unexplained evidence fails the baseline exception.
- Corrections retain the goal, accepted architecture, risk tier, effective scope,
  dependencies, data/protected boundaries, and external consequences. Repeated
  failure requires new diagnostic evidence, not an arbitrary attempt-count gate
  or an uncontrolled loop.
- Conditional staging/one-local-commit permission is a separate explicit owner
  instruction, activated only after exact candidate verification, review,
  finding disposition, and owner acceptance. W2 grants none.
- Final candidate acceptance and consequential architecture/product, privacy,
  destructive/migration, scope, publication, deployment, external write, and
  financial decisions remain human-controlled.
- Durable rules stay in their repository owners; task handoffs cite them.
- Existing session/review documents' W1 version references describe inherited
  preflight/review requirements, which remain applicable. Their requirement for
  separately explicit local-commit authority remains satisfied by the proposed
  conditional instruction; acceptance alone still grants none. No other
  canonical source change is required for these semantics.
- Rollback would restore only the W2 paths under separate applicable authority;
  no runtime/data migration or deployed behavior exists.

## Candidate and verification disposition

The candidate is uncommitted and contains only the three primary paths plus
`docs/reviews/engineering-workflow-v1-2-evidence-2026-09-16.md`.
No generated source changed, and generated synchronization is checked rather
than manufacturing a generated diff. No implementation runtime or test was added.

### Candidate preparation verification

The post-implementation run before this evidence update observed:

| Command (from repository root) | Observed result |
| --- | --- |
| `PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p 'test_public_surface.py'` | Exit 1; 19 tests, the same three baseline failures |
| `PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p 'test_active_state.py'` | Exit 0; 42 tests passed |
| `PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p 'test_atlas_readiness.py'` | Exit 0; 19 tests passed |
| `PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 python3 -m unittest discover -s tests -p 'test_*.py'` | Exit 1; 562 tests, three baseline failures, one skip; 87.733 seconds |
| `PYTHONDONTWRITEBYTECODE=1 ./atlas validate` | Exit 0; valid, no errors/warnings |
| `PYTHONDONTWRITEBYTECODE=1 ./atlas missing` | Exit 0; no missing definitions |
| `PYTHONDONTWRITEBYTECODE=1 ./atlas sync` | Exit 0; synchronized, zero errors/warnings |
| `git diff --check` | Exit 0 |
| `git diff --cached --name-status` | Exit 0; empty |
| `git diff --exit-code -- tests tools docs/current-state.json docs/current-mission.md docs/aiden-context.md docs/infrastructure-snapshot.md` | Exit 0; empty |

Failure names and affected path/line signatures match the pre-mutation baseline.
The legacy-identity comparison, applying the test's own self exclusion, confirms
only the excluded September 8 record as unexpected, with no missing dispositions.
Both excluded owner-file hashes match the baseline. No new or worsened failure
was found; the full suite remains failing with approved out-of-scope debt.
The existing skip remains visible. No test rule or excluded source was changed.

The full three-file tracked diff and complete new evidence record were inspected.
Status contains only those four W2 paths plus the two original untracked files.
The candidate remains uncommitted on the original base, with nothing staged.

### Preparatory independent review

A fresh read-only reviewer, `w2_review`, inspected the complete three-file diff,
the full evidence record, the accepted six-part request, and applicable session,
lifecycle, review, collaboration, and knowledge-authority contracts.
Disposition: no actionable findings; no blocking or material semantic defect
identified. Existing W1 references do not introduce a materially conflicting
rule. The reviewer did not rerun tests or independently inspect execution logs,
so execution remained implementation-supplied evidence at this stage. This
review is explicitly preparatory, not the final frozen-candidate review.

No corrective edit was required. The only subsequent mutation is this evidence
update recording observed preparation checks and review disposition.

### Closing verification and review boundary

This evidence update is itself a candidate mutation. The results above are
preparation evidence, not a claim to have verified this later tree. After this
record is frozen, rerun the exact focused/full/Atlas/diff commands above and
fresh preservation/path checks, then obtain a fresh adversarial independent
review of all four exact final files. The closing owner-facing handoff carries
that final execution and review attestation, including candidate file digests;
it must distinguish unchanged baseline debt and must not claim acceptance.
Any subsequent repository mutation invalidates that closing attestation and
requires renewed final verification and applicable review.

Owner acceptance, local commit, publication, and deployment remain unperformed.
The remaining known limitation is unrelated approved baseline debt; final
readiness depends on the closing exact-candidate verification and review.
