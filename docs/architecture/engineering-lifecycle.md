# Engineering Lifecycle Architecture

## Purpose

The Engineering Lifecycle defines how an authorized checkpoint becomes a
verified candidate, receives required review and owner decisions, and may later
be published or deployed. It makes corrections efficient without weakening
scope, evidence, or authority boundaries.

## Core Principle

Focused verification supports implementation. One tier-appropriate broad check
establishes the final candidate only after the last in-scope mutation.

## Lifecycle Flow

    Accepted brief and bounded implementation authority
        ↓
    Environment preflight
        ↓
    Implement with focused verification
        ↓
    Document, generate, validate, and synchronize
        ↓
    Final broad/native verification after the last mutation
        ↓
    Required independent review
        ↓
    Bounded correction and renewed final evidence when needed
        ↓
    Explicit owner acceptance
        ↓
    Separately authorized publication or deployment

Repository state, Atlas guidance, verification, and review report facts; none
of them silently advances another lifecycle gate or grants authority.

## Verification Sequencing

Focused tests run when a useful baseline exists, after coherent increments,
and after each correction against the affected behavior and nearby regression
boundary. Handoff alone or rewriting a report outside the candidate does not
require rerunning tests; a candidate mutation still requires final verification.

Final broad verification is proportional:

- Tier 1 uses the smallest appropriate broad check; a repository-wide suite is
  required only for shared behavior or test infrastructure.
- Tier 2 uses one final capability-wide or repository-wide native suite chosen
  in the checkpoint brief.
- Tier 3 uses one final full appropriate native suite, including relevant
  adversarial or negative paths.

The recorded final run must follow the final repository mutation. Any later
mutation invalidates that run as final evidence for the resulting tree. When a
review causes corrections, group them, use focused tests while correcting, and
run the broad suite once after the last correction.

Synthetic selected, idle, and error fixtures must be isolated from mutable live
state. A canonical file or live data root may be used only when an explicitly
named smoke or authorized live verification is the subject.

## Baseline-Aware Verification

Establish a pre-mutation baseline with the relevant command, accepted native
environment, candidate/base identity, and failure signatures (test/check,
affected path, and assertion or behavior). Preserve enough evidence to compare
the final run, and confirm unrelated owner files and test rules are unchanged.
Do not expose protected values to document a signature.

A pre-existing failure is non-blocking for the checkpoint only when all of the
following are demonstrated:

- it predates checkpoint mutations;
- its cause lies outside effective checkpoint scope;
- its failure signature and relevant underlying inputs remain unchanged;
- the checkpoint neither conceals nor worsens it; and
- the failure, evidence, and remaining uncertainty are explicitly reported.

Compare the actual final focused and broad results with that baseline. A
matching failure count alone is insufficient. Report the command's failing
exit status and each baseline failure separately from new checkpoint failures;
approved baseline debt does not make a full suite pass. If evidence is missing
or a difference is unexplained, treat it as a failure, not baseline debt.

Do not delete excluded files, alter tests/policy, filter required tests, or
broaden scope to manufacture a passing result. A new or changed failure receives
automatic correction when safely within the accepted scope. Stop only when
diagnosis or repair requires a consequential boundary decision or cannot be
completed safely in scope. Baseline debt is not acceptance of unrelated work,
permission to repair it, or proof of its general safety.

## Correction Continuation

Ordinary implementation, evidence creation, registered generation, correction,
and verification continue automatically without owner interruption inside the
accepted checkpoint. Effective scope is the primary and mechanically derived
scope defined in `docs/standards/engineering-collaboration.md`.

A correction continues without restarting design or authorization only when
all of these remain unchanged:

- goal and observable result;
- risk tier and accepted architecture;
- effective scope and authorized operations;
- data, dependency, configuration, external-target, and protected boundaries
  and external consequences; and
- rollback, verification, and stop conditions.

After an in-scope correction, rerun affected focused checks. Tier 2 review
confirms a material affected delta. A Tier 3 blocking correction requires a
fresh final adversarial review after final verification.

Stop for an owner decision when authority is ambiguous, protected or
destructive behavior would exceed explicit authority, or a material alternative
or tradeoff requires judgment. Redesign or seek exact scope expansion when
non-derived scope, tier, accepted architecture, dependency, configuration,
external consequences, protected boundary, or observable result must change,
or when rollback or verification cannot remain safely bounded. Evidence
creation, generation, and an ordinary repair are mechanics, not new decision
gates when they remain within effective scope.

## Anti-Loop Stops

Repeated failures trigger diagnosis and comparison with prior attempts, not an
automatic stop based on a fixed attempt count. Continue only with a concrete,
evidence-backed corrective action that remains safely inside the accepted
checkpoint; do not repeat ineffective actions without new evidence.

Stop when that assessment shows:

- a consequential scope, tier, architecture, dependency, configuration,
  external-action, destructive, or protected-boundary decision is required;
- material alternatives require owner judgment;
- architecture and implementation cannot agree inside the accepted design;
- evidence cannot truthfully identify the candidate or its verification and
  cannot be repaired safely inside scope;
- verification cannot run in the accepted environment without unauthorized
  remediation; or
- diagnosis cannot establish a safe in-scope repair or a clear goal, current
  state, risk, and next decision.

Record attempted corrections, relevant evidence, and the exact unresolved
boundary. A new safe in-scope repair may proceed without repeated approval;
an unresolved consequential choice remains human-controlled.

## Responsibilities

The lifecycle preserves architecture, generated ownership, repository
validation and synchronization, complete-diff inspection, finding disposition,
and human-controlled mission advancement. Atlas may observe and recommend; the
owner approves direction, acceptance, publication, deployment, and external
writes.

## Non-Responsibilities

The lifecycle does not replace human judgment, treat generated context as
canonical, hide uncertainty, infer authority, auto-advance missions, or require
repeated full-suite runs without a new final candidate.
