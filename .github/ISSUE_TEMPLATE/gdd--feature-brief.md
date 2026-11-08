---
name: 'GDD: Feature Brief'
about: Feature Requirements Document using GameEARS Requirement
title: "[GDD] "
labels: _Game Design, _Requirement
assignees: ''

---

# [Feature title]

**ID:** [Stable ID] 
**Engine:** 
**Status / revision / date:** [Values] 
**Project / phase:** [Project and phase]  
**Owner / reviewers:** [Names]  
**Reviewers:**
**Parent / pillar / canonical issue:** [Links] 
**Quality level:** [Current → target]

# Primary Goal

[Short free-form description of the desired player outcome.]

## User Story

_As a [player/persona], I’d like to [capability], so that [value]._

## Formalized re-write

SMART and WHWWW are complementary prompts, not exact equivalents. Include feasibility under Attainable and design alignment under Relevant.

| SMART | WHWWW | Description |
| -- | -- | -- |
| Specific | What | [Design intent and bounded outcome.] |
| Measurable | How | [Observable behavior, measures, and acceptance links.] |
| Attainable | Why | [Feasibility evidence, capacity, dependencies, and why this can deliver the intent.] |
| Relevant | Who | [Beneficiaries and responsible systems; alignment with story, pillar, and phase.] |
| Timebound | When | [Date or milestone/build and decision owner. Label TBD honestly.] |

## Design intent, scope, and player flow

[Free-form GDD explanation, normal flow, feedback, failure and recovery.]

- **Included:** [Current commitments.]
- **Excluded / deferred:** [Boundaries.]
- **Assumptions:** [Unconfirmed choices.]

## Player flow

# Requirements

Use stable IDs and one independently testable response per requirement where practical. State priority explicitly; Secondary does not automatically mean optional. Game-EARS: When [event], while [context], the [system] shall [response]. Keep rationale separate. Use While for state rules, If for unwanted conditions, and Where for optional capabilities.

## Primary

**R-00 [priority] — Requirement:** [The system shall / Game-EARS behavior.]

**Rationale:** [How this supports the user story.]

**Inspiration:** [Attributed example/reference, or none; distinguish inspiration from a binding decision.]

## Secondary

| ID / priority | Requirement | Rationale |
| -- | -- | -- |
| R-01 / [priority] | [Behavior.] | [Intent.] |

## Feedback

| ID / priority | Requirement | Rationale |
| -- | -- | -- |
| R-02 / [priority] | [Visible, audible, tactile, accessible feedback.] | [Intent.] |

## Environmental

| ID / priority | Requirement | Rationale |
| -- | -- | -- |
| R-03 / [priority] | [Platform/state/interruption behavior.] | [Intent.] |

# Designer Notes

- [Experience, balancing, art/audio, accessibility, localization, and references.]
- [Explain alternatives or intent without hiding required behavior here.]

# Technical Notes

- [Constraints and integration boundaries; link detailed architecture/specifications.]
- [Performance/timing measures need units, clock/reference, boundaries, build, hardware, and procedure.]

## Dependencies and open decisions

| Item / blocking? | Owner | Decision / next action / needed by |
| -- | -- | -- |
| [Item] | [Name] | [Action and date/milestone] |

# Acceptance and Delivery

## Acceptance criteria

| ID / requirement links | Setup and action | Pass condition |
| -- | -- | -- |
| AC-01 → R-01 | [Procedure/data/context.] | [Observable result and boundaries.] |

## Player experience evaluation

[Question, participants, procedure, build, proposed or approved decision threshold, and resulting action. Separate usability/enjoyment evidence from functional correctness.]

## Implementation tasks

| Task / owner | Deliverable | Requirement / acceptance links |
| -- | -- | -- |
| [Task / name] | [Work and estimate/milestone.] | [IDs and issue links.] |

## Review and acceptance record

- **Ready review:** [Reviewer/date/revision; resolved blockers and scope decision.]
- **Acceptance:** [Decision, reviewer, date, build, criteria evidence, quality evidence, playtest decision, exceptions and owners.]
- **Change history:** [Revision/date/change/affected requirements, tasks, tests.]

# Quality Check

Check against evidence for the brief; these boxes do not report implementation completion. Explain unchecked items and identify their resolution owner.

- [ ] Complete — [Flows, boundaries, failure/recovery, dependencies, and acceptance covered.]
- [ ] Correct — [Matches reviewed design and verified facts.]
- [ ] Concise — [No unnecessary repetition or hidden requirements.]
- [ ] Feasible — [Capacity and technical evidence support delivery.]
- [ ] Necessary — [Each requirement supports the agreed outcome.]
- [ ] Prioritized — [Priority and deferrals are explicit.]
- [ ] Unambiguous — [Terms, triggers, states, and boundaries have one interpretation.]
- [ ] Verifiable — [Each required behavior has a measurable pass/fail method.]
- [ ] Consistent — [No conflict internally or with referenced documents.]
- [ ] Traceable — [Story/goal → requirements → tasks/specs → tests → build/evidence.]

# References

- [Canonical design, technical, inspiration, and evidence links.]
