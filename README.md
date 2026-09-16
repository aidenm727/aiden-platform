# Aiden Platform

> A human-directed engineering platform for applied AI, deterministic tooling,
> and self-hosted infrastructure.

`aiden-platform` is the root Platform engineering repository for shared systems,
Platform-wide architecture, cross-domain contracts, and explicitly assigned
responsibilities. It supports useful capability with explicit authority,
reproducible evidence, and replaceable technology.
It is not a production SaaS platform, proof of continuous uptime, or a claim of
autonomous operation.

The human owner chooses goals, grants bounded authority, reviews evidence, and
accepts consequences. Repository state, Atlas, generated context, and AI
assistance never grant permission.

## What Exists Today

Here, **implemented** means repository code and tests exist, **operational
evidence** means a dated observation or use record exists, and **future** means
no implementation or operation is claimed.

| Capability | Status | Proof |
| --- | --- | --- |
| School Learning | Implemented; used in a bounded owner pilot | [Architecture](docs/architecture/school-learning.md), [implementation](tools/school_learning/), [tests](tests/test_school_learning.py), [pilot evaluation](docs/reviews/school-learning-v0-1-pilot-evaluation-2026-07-21.md) |
| Atlas and Workflow v1.2 | Implemented; operational as the repository workflow | [`./atlas`](atlas), [typed state](docs/current-state.json), [W2 evidence](docs/reviews/engineering-workflow-v1-2-evidence-2026-09-16.md) |
| Task-scoped context compilation | Implemented library capability; no general public CLI claim | [Architecture](docs/architecture/task-scoped-agent-context-compilation.md), [compiler](tools/atlas/platform/context_compilation/), [selection](tools/atlas/platform/reasoning/context_selection.py), [tests](tests/test_context_compilation.py) |
| Self-hosted infrastructure | Dated operational evidence; continuous state is not claimed | [Public-safe infrastructure](docs/infrastructure.md), [virtualization record](docs/infrastructure-virtualization.md), [service capabilities](docs/services.md) |

Implemented today: deterministic repository engineering tools, reproducible
task-scoped context compilation, and an owner-controlled School Learning
workflow.

Operational evidence: a small self-hosted environment has supported core
networking, observability, backup, virtualization, and selected services.
Public records are sanitized and time-bounded; they do not prove continuous
availability.

Future work: knowledge sovereignty, demonstrated recovery, and local-AI
experiments remain planned or exploratory until a dated evidence record
establishes implementation and operation.

## Architecture

Canonical authority is source-scoped. This root record, selectively earned
specialized engineering repositories, restricted operational records, external
systems, and live systems may own distinct responsibilities. Atlas and typed
state describe this repository; they are not a universal Platform ledger.
See [Repository Architecture](docs/architecture/repository.md) for ownership.

```text
Human owner
  ├── goals, authority, review, acceptance
  │
  ▼
Public engineering record
  ├── architecture and standards
  ├── deterministic tooling and tests
  ├── capability implementations
  └── sanitized evidence
          │
          ├── explicit bounded handoff ──► Replaceable AI providers/runtimes
          │
          └── public-safe patterns ─────► Self-hosted execution environments

Future restricted operational source, separately designed
  └── exact non-secret desired state when a durable artifact is identified
      (current reality remains owned by live systems and fresh observation)
```

## Proof in Practice

### School Learning

The [School Learning architecture](docs/architecture/school-learning.md) defines
a local data contract, grounded Guided Study Handoff, and explicit
insufficient-evidence behavior. The [implementation](tools/school_learning/),
[negative-path tests](tests/test_school_learning.py), and [dated pilot
evaluation](docs/reviews/school-learning-v0-1-pilot-evaluation-2026-07-21.md)
show the chain from an owner problem through real use and correction. Personal
course material, answers, and learning history remain outside Git.

### Task-Scoped Context Compilation

The [context architecture](docs/architecture/task-scoped-agent-context-compilation.md)
is implemented as bounded snapshot, selector, selection, materialization,
validation, digest, and compiler layers under
[`tools/atlas/platform/context_compilation/`](tools/atlas/platform/context_compilation/).
The [snapshot](tests/test_context_snapshot.py),
[selection](tests/test_context_selection.py), and
[materialization](tests/test_context_materialization.py) tests cover immutable
identity, provenance, byte budgets, omissions, and consumer constraints. This
is a library capability, not a claim of a general public CLI or production
service.

### Atlas and Workflow v1.2

Atlas turns registered repository facts into deterministic inspection,
validation, synchronization, review, and next-action reports. The
[canonical state](docs/current-state.json),
[collaboration standard](docs/standards/engineering-collaboration.md),
[readiness tests](tests/test_atlas_readiness.py), and
[W2 evidence](docs/reviews/engineering-workflow-v1-2-evidence-2026-09-16.md)
show how typed state remains separate from owner authority.

## Engineering Quality

```text
real problem
→ owner decision
→ bounded implementation
→ negative/adversarial tests
→ independent review
→ correction
→ reproducible verification
→ owner acceptance
```

Verification counts are dated outcomes, not permanent claims about the current
suite. For example, W1 recorded 406 passing tests and one skip on 2026-08-02;
the linked evidence and Git history own that historical result. On 2026-08-06,
local post-rename finalization verification passed 429 tests with one skip. The
exact candidate then received fresh adversarial review and owner acceptance.
R1 is recorded as published and complete; the accepted lifecycle correction
was published on 2026-08-07 as immutable R1 publication commit
`483f1111257c9b1608c100cb88c8304a17d85314`.

## Inspect or Run

From the repository root in the current checkout:

```bash
PYTHONDONTWRITEBYTECODE=1 ./atlas bootstrap
PYTHONDONTWRITEBYTECODE=1 ./school --help
PYTHONPATH=tools PYTHONDONTWRITEBYTECODE=1 \
  python3 -m unittest discover -s tests -p 'test_*.py'
```

`./atlas bootstrap` inspects repository state; it does not authorize work.
School Learning keeps personal data outside Git. The canonical public clone is:

```bash
git clone https://github.com/aidenm727/aiden-platform.git
```

## Public and Private Boundary

| Fact class | Canonical owner |
| --- | --- |
| Root/shared Platform architecture, standards, code, tests, repository state and evidence within assigned scope | This public repository |
| Independently substantial project/system engineering | An explicitly designated specialized repository when earned; Homelab is the first accepted candidate |
| Sanitized infrastructure patterns and dated public evidence | This public repository |
| Exact non-secret Homelab desired operational state | A separately designed restricted canonical source when a concrete durable operational artifact is identified |
| Secret values, private keys, tokens, and recovery keys | Secret manager or protected operational storage; never Git |
| Current live reality | Live systems and fresh observation |
| GitHub description, topics, settings, rules, and integrations | GitHub itself; only dated summaries belong here |

The canonical boundaries and trigger for a future restricted source are in
[Repository Architecture](docs/architecture/repository.md).

## Current and Future

The September 2026 operating-model recalibration accepts Homelab as a
specialized-repository candidate; it does not create that repository or move
content. Suitable capabilities may incubate through natural or conversational
use and earn software through recurring need. AI/tool recommendations remain
advisory and human-overridable under the existing
[AI Operating Model](docs/architecture/ai-operating-model.md).

The repository-local lifecycle below concerns the earlier repository-identity
R1 and published engineering phases, not acceptance or publication of this
September recalibration.

The [canonical state](docs/current-state.json) keeps W2 / Workflow v1.2 as the published phase,
records R1 as owner-accepted, published, and complete, and intentionally
selects no implementation checkpoint. S1, F2, F3, and all other future work
remain unselected; the next decision is owner selection of future work. The
live GitHub repository is `aidenm727/aiden-platform`; the verified rename,
approved description and topics, redirect behavior, profile pin, connector,
and local origin update are recorded in the dated R1 evidence. The accepted
lifecycle correction was published on 2026-08-07 as immutable R1 publication
commit `483f1111257c9b1608c100cb88c8304a17d85314`.

Aiden Platform began as a ThinkPad T430 homelab and grew into a broader personal
engineering platform. Current delivered capability centers on School Learning,
Atlas/Workflow v1.2, task-scoped context compilation, and public-safe dated
infrastructure evidence. Local AI, a private operations repository, broader
knowledge sovereignty, and additional recovery proof remain future or
conditional work.

## Navigate Deeper

- [Vision and human authority](docs/vision.md)
- [Platform architecture](docs/architecture/platform.md)
- [Canonical current state](docs/current-state.json)
- [Dated review evidence](docs/reviews/)
- [Full documentation map](docs/docs-map.md)
