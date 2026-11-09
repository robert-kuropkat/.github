---
name: __ Technical Design
about: Top Level Technical Design Document
title: "[TDD] Technical Design"
labels: "-Top Level Document, _Technical Design"
assignees: ''

---

# [Game Title] — Technical Design Document

**Document ID:** TDD-001  
**True parent:** [GDD issue link — exactly one parent]  
**Canonical issue:** [Link]  
**Owner / reviewers:** [Names and roles]  
**Status / revision / reviewed date:** [Values]  
**Phase / target build or milestone:** [Values; unresolved dates remain TBD]  
**Current / target Level of Quality:** [Values and measurable phase criteria]

# Purpose and Scope

## Overview

[Describe how the technical approach will realize the game experience. Summarize major implementation choices, boundaries, and the most important risks in plain language.]

The GDD and Feature Briefs define intended behavior and player value. This TDD defines the shared implementation architecture and constraints that realize that behavior. Child Design Specifications define detailed implementation; Infrastructure Specifications define supporting capabilities; Test Plans define verification. Tasks execute bounded work under one owning document.

This document describes implementation; it does not replace the software, tests, or acceptance evidence. A technical decision that changes player-facing behavior must be reconciled with the affected Feature Brief before adoption.

## Scope by Phase

| Phase | Included technical capabilities | Excluded / deferred | Target quality / milestone |
| -- | -- | -- | -- |
| [Demo] | [Capabilities] | [Boundaries] | [Criteria and milestone] |

## Relationship Register

| Relationship | Document / revision | Meaning |
| -- | -- | -- |
| True parent | [GDD] | Canonical ownership and publication placement |
| Implements | [Feature Brief IDs and revisions] | Requirements realized by this technical design |
| Constrained by | [ADD, SDD, platform, production constraints] | Rules the technical approach must respect |
| Owns | [Design Specs, Infrastructure Specs, Test Plans] | True child documents; indexed below |
| References | [Other canonical documents] | Supporting information, without another parent |

# Feature Coverage and Traceability

Link requirements rather than copying their complete text. Include each in-scope requirement or an explicit range with identical coverage. Mark uncovered requirements and blockers honestly. Local IDs must include their feature prefix when referenced across briefs, for example `FB-INPUT-01 / R-03`.

| Feature / revision and requirement IDs | Responsible subsystem | Technical decision / constraint | Design or infrastructure spec | Test Plan / acceptance IDs | Coverage / blocker |
| -- | -- | -- | -- | -- | -- |
| [FB / R IDs] | [Subsystem] | [TD / TC IDs] | [Link or planned ID] | [Link and AC IDs] | [Designed / pending / deferred] |

Do not use “designed” to mean implemented or verified. Keep implementation status in tasks and verification results in test-run evidence.

# System Architecture

## Architectural Overview

[Free-form explanation and a small component diagram: major systems, responsibilities, connections, and external services. Distinguish current implementation, accepted design, and proposals.]

## Subsystem Responsibilities

| Subsystem | Owns | Receives / produces | Does not own | Detailed specification |
| -- | -- | -- | -- | -- |
| [System] | [Responsibilities/state] | [Inputs/outputs] | [Important boundary] | [Link] |

## Shared Execution and Lifecycle

- **Startup and shutdown:** [Initialization order, dependency readiness, cleanup.]
- **Scene/session lifecycle:** [Persistent services, scene ownership, restart and invalidation rules.]
- **State transitions:** [Shared menu, gameplay, pause, loading and recovery states; authority for each transition.]
- **Scheduling and clocks:** [Update model, authoritative time sources, conversion boundaries and pause behavior.]
- **Event ownership:** [Who emits/consumes events, subscription lifecycle, ordering and duplicate prevention.]

Keep feature-specific state machines and algorithms in child Design Specs.

# Interfaces, Data, and Persistence

## Shared Contracts

| Contract ID | Producer → consumer | Data / units / time reference | Ordering / lifecycle / failure policy | Owning specification |
| -- | -- | -- | -- | -- |
| [IF-01] | [Systems] | [Fields and semantics] | [Guarantees] | [Link] |

## Data Ownership and Storage

- **Content/configuration:** [Authoring format, source of truth, validation and runtime loading.]
- **Runtime state:** [Authority, lifetime and reset rules.]
- **Player settings and saves:** [Storage ownership, schema versions, migrations, defaults, corruption and write-failure handling.]
- **External services / personal data:** [Needed services, data flows, credentials/configuration handling; mark not applicable when appropriate.]

# Technical Requirements and Quality Constraints

Feature Briefs remain authoritative for player-facing requirements. Use `TC-xx` for shared technical constraints, with rationale and verification. Use Game-EARS phrasing when an event or state makes the behavior clearer. Do not invent numeric budgets merely to fill the table.

| ID / priority | Constraint | Rationale / source | Measurement conditions and pass criterion | Owner / state |
| -- | -- | -- | -- | -- |
| [TC-01 / Must] | [Observable technical rule] | [FB / platform / decision link] | [Procedure, units, boundaries, build/hardware] | [Name / proposed or accepted] |

Consider frame time, event timing, memory, loading, supported devices, accessibility integration, save reliability, and recovery as relevant. Distinguish software event timing from physical end-to-end latency. Cross-cutting budgets must identify who allocates and maintains them.

# Development Tools and Processes

## Overview

[Summarize the supported development environment and repeatable workflow.]

## Game Engine

[Exact engine/editor version, render pipeline, relevant project settings, package versions and upgrade policy.]

## Version Control

[Repository, branching/review conventions, Unity asset/meta handling, large/binary files, merge policy and canonical issue links.]

## Delivery Platform(s)

[Operating systems, distribution channels, minimum/test hardware, device matrix and platform-specific constraints. Distinguish confirmed targets from proposals.]

## Frameworks and Assets

| Dependency / version | Purpose | Owner / integration point | License / upgrade or replacement considerations |
| -- | -- | -- | -- |
| [Package or asset] | [Use] | [System / owner] | [Constraints] |

## Development Tools

[IDE, content tools, profiling/debugging tools, test tools and required versions/setup links.]

## Build Process

- **Local build:** [Prerequisites, entry point, configuration and output.]
- **Automated build:** [Trigger, validation, build identifier and artifact storage; or explicitly deferred.]
- **Environments:** [Development/test/release differences and configuration ownership.]
- **Delivery and recovery:** [Packaging, smoke test, release handoff and rollback/recovery.]
- **Detailed pipeline:** [Infrastructure Specification link when needed.]

# Content and Discipline Integration

- **Art / animation:** [Import conventions, runtime ownership, budgets and ADD constraints.]
- **Audio:** [Playback/events, synchronization, mixing ownership and SDD constraints.]
- **UI / accessibility / localization:** [Shared UI integration, input prompts, localization flow and required alternate feedback.]
- **Validation:** [How invalid or incompatible content is detected and reported.]

Link discipline rules to their canonical documents. Do not duplicate asset catalogues or character sheets here.

# Verification Strategy and Diagnostics

## Verification Approach

[Which risks require unit/integration tests, standalone-build tests, hardware checks, profiling or playtests. Identify environments, fixtures, deterministic test hooks and evidence format. Test Plans own detailed cases and expected results.]

## Observability and Debugging

[Useful logs, identifiers, debug views and capture/replay support. Define what evidence lets a tester distinguish input, timing, content and presentation defects.]

## Integration and Regression

[Integration sequence, existing-behavior baseline, shared regression checks and build acceptance handoff. Feature acceptance remains tied to the brief’s criteria and player evaluation.]

# Technical Decisions, Risks, and Open Questions

## Decision Log

| ID / state / date | Decision and rationale | Alternatives / tradeoffs | Affected features/specs/tests | Decision owner |
| -- | -- | -- | -- | -- |
| [TD-01 / proposed] | [Choice and reason] | [Options] | [Links] | [Name] |

## Risks and Unresolved Decisions

| ID | Risk / question | Impact / blocking scope | Owner | Experiment / mitigation / next action | Needed by |
| -- | -- | -- | -- | -- | -- |
| [Risk] | [Unknown] | [Affected work] | [Name] | [Action and evidence] | [Milestone/date] |

# Child Document Register and Handoff

| ID / true child type | Scope | Source requirements / constraints | Owner | Status / link |
| -- | -- | -- | -- | -- |
| [SPEC-… / Design Specification] | [Detailed implementation problem] | [FB/R, TC, TD IDs] | [Name] | [State/link] |
| [INFRA-… / Infrastructure Specification] | [Supporting capability] | [Constraints] | [Name] | [State/link] |
| [TEST-… / Test Plan] | [Verification scope] | [FB/R/AC and spec links] | [Name] | [State/link] |

Design Specs and Test Plans are sibling children of this TDD. A Test Plan references the specs it verifies without acquiring additional parents. Each implementation task has one owning spec; each test-preparation/execution task has one owning Test Plan. Cross-cutting tasks choose one accountable parent and reference other affected documents. Add a shared spec if the work genuinely needs a shared design boundary.

The earlier Feature Brief’s task table is a proposed breakdown, not a second ownership tree. Link its work packages to the actual spec-owned or plan-owned task issues when created.

## Ready to Create Specs and Test Plans

- [ ] Relevant Feature Brief revisions, scope and requirement IDs are identified.
- [ ] Responsible systems, interfaces and shared constraints are sufficiently clear for this slice.
- [ ] Blocking decisions are resolved, or a bounded investigative task has an explicit question and deliverable.
- [ ] Required child documents have owners and defined boundaries.
- [ ] Verification approach and phase quality criteria are identified.

The entire game architecture need not be finished to develop the first slice. Mark unrelated sections “not yet designed,” with owners where needed. Specs and Test Plans can develop together; implementation readiness is assessed for their bounded scope.

# Quality Check and Review History

- [ ] Complete
- [ ] Correct
- [ ] Concise
- [ ] Feasible
- [ ] Necessary
- [ ] Prioritized
- [ ] Unambiguous
- [ ] Verifiable
- [ ] Consistent
- [ ] Traceable

For each unchecked item, record the gap, owner and affected scope. These checks assess documentation readiness, not feature completion.

| Revision / date | Reviewer / decision | Change and reason | Impacted documents / tasks / tests |
| -- | -- | -- | -- |
| [Values] | [Proposed / reviewed / accepted] | [Summary] | [Links] |
