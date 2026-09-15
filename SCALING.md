# SCALING.md

## Purpose

This document is the source for scaling this repository's structure up or
down with project complexity. It is grounded in two references:

- Project Management Institute, *A Guide to the Project Management Body of
  Knowledge (PMBOK Guide)*, 6th edition, 2017.
- Erik W. Larson and Clifford F. Gray, *Project Management: The Managerial
  Process*, 7th edition, McGraw-Hill.

`README.md` Section 7 states the general principle: add complexity only when
it has a clear function, is not already covered, and its value exceeds its
maintenance cost. This document makes that principle concrete, area by area,
using the complexity signals both references treat as the point where a
lean practice stops being sufficient.

This file is never copied into a project. It stays at the repository root
and is consulted in place, the same way `AGENTS.md` and `README.md` are.

## How to Use This Document

For each area below, compare the project's actual situation against the
complexity signals listed. If none apply, the lean default already in the
templates is sufficient; do not add anything preemptively. If one or more
signals apply, add the escalation described, adapted to the project, not
copied wholesale.

Record the decision to scale an area, and why, as a decision in
`decision_log.md` (a new `DEC-###` entry). This keeps the choice traceable
and prevents an agent or a future collaborator from wondering why a project
has more structure than the default template.

A human or an AI agent working on an already-bootstrapped project should
read this file whenever project_definition.md, the schedule, or the work
itself suggests the project is more complex than the lean default assumes,
not only at the start.

## Scope

**Lean default:** `project_definition.md` lists deliverables (`DEL-###`)
with an acceptance criterion each. `project_plan.md` lists work packages
(`WP-###`) that produce or support a deliverable. This is a flat list, not a
decomposition.

**Complexity signals** (PMBOK 5.4, Larson & Gray 4.3): a work package cannot
be reliably estimated, assigned to a single owner, or completed without
further breakdown; a deliverable has enough internal structure that
tracking it as one line loses control; more than one team or discipline
contributes to the same deliverable.

**Escalation:** decompose the affected deliverable into a real Work
Breakdown Structure: `DEL-001` breaks into sub-work-packages
(`WP-001.1`, `WP-001.2`, ...) each still following the work package rules
in `README.md` Section 6. For a complex deliverable, add a short WBS
dictionary entry per element (description, acceptance condition, owner),
either as extra columns in the work breakdown table or as a short
sub-section. Stop decomposing once every terminal element can be reliably
estimated and owned by one person.

## Schedule

**Lean default:** one authoritative schedule (`01_Planning/schedule.md` or
`.xlsx`) per `README.md` Section 2, with activity, work package, owner,
planned dates, status, and dependencies. `project_status.md`, when used,
adds a simple quantitative rollup: work packages complete and milestones
met, counted directly from the plan and schedule, not tracked separately
(Larson & Gray 13.3's Percent Complete Rule at its leanest).

**Complexity signals** (PMBOK 6.5, Larson & Gray 6.4-6.6): more than roughly
20-30 activities where dependency logic stops being obvious by inspection;
multiple critical paths; resource conflicts across activities; a client or
sponsor needs forecast dates, not only planned ones.

**Escalation:** add the optional extension columns already described in
`04_Templates/template_schedule.md` (forecast finish, actual finish,
variance) as they become useful, and consider a proper network diagram
(activity-on-node, per Larson & Gray Chapter 6) built in scheduling
software once dependency logic is no longer manageable in a flat table.

## Cost

**Lean default:** `project_definition.md` has a Budget field under
Conditions (approved amount, source, fixed or estimated, or — when the
project does not track one). `project_plan.md`'s work breakdown table has
an Estimated Cost column per work package, and Progress monitoring
includes estimated versus actual cost when a budget exists.

**Complexity signals** (PMBOK Chapter 7, Larson & Gray Chapters 5 and 8):
the project has an approved budget from a client, sponsor, or grant;
more than one funding source; cost variance needs to be reported to
someone outside the project; resources have materially different costs
that affect decisions.

**Escalation:** once a per-work-package cost estimate exists (the lean
core), add actual-cost tracking and a simple variance (estimated vs.
actual) when someone outside the project needs to see it. Move to a full
cost baseline and earned value tracking (planned value, earned value,
actual cost, cost and schedule performance indexes, estimate at
completion, per Larson & Gray Chapter 13) only when the project is funded
externally, audited, or large enough that a simple variance stops being
informative.

## Quality

**Lean default:** the acceptance criterion column in the deliverables table
(`project_definition.md`) and the success criteria table serve as a lean
quality gate: a deliverable or the project is not accepted until its
stated condition is observably met.

**Complexity signals** (PMBOK Chapter 8): the deliverable has regulatory,
safety, or contractual quality standards that exist independently of the
project's own acceptance criteria; quality failures are costly enough to
justify inspection or testing as a distinct activity; more than one person
needs to sign off on quality, not only accept the deliverable.

**Escalation:** add a quality standards reference to the relevant
deliverable or work package (which standard applies, who verifies it), and
a distinct quality control activity in the schedule when testing or
inspection is real, separate work, not just implied by "acceptance."

## Resources

**Lean default:** one owner per work package, activity, risk, and
deliverable, as required by `README.md` Section 6.

**Complexity signals** (PMBOK Chapter 9, Larson & Gray 4.7 and Chapter 8):
more than one person or role contributes meaningfully to the same item,
so "owner" alone does not show who else is involved; resources are shared
across activities and can become a bottleneck; the project competes with
other projects for the same people.

**Escalation:** add a lean responsibility matrix (a RACI-style table:
who is Responsible, Accountable, Consulted, Informed per work package or
deliverable) when more than one role is genuinely involved. Add resource
loading or leveling to the schedule (Larson & Gray 8.4-8.6) only once
resource conflicts across activities are a real, recurring problem, not a
hypothetical one.

## Communications

**Lean default:** `project_plan.md` Section 5 has one line for review
frequency. `project_status.md`, when used, is the situational snapshot.

**Complexity signals** (PMBOK Chapter 10, Larson & Gray 4.8): more than one
audience needs different information at different cadences (for example, a
sponsor wanting a monthly summary versus a team needing weekly detail);
communication failures have already caused rework or missed expectations;
the project spans organizations or time zones.

**Escalation:** add a short communications table (audience, information
needed, frequency, channel, owner) to `project_plan.md` once more than one
audience needs materially different information. Do not build this for a
single stakeholder who simply reads the schedule.

## Risk

**Lean default:** the risk and opportunity table in `project_plan.md`
Section 4 already covers identification, exposure, owner, response, and
status, matching Larson & Gray Chapter 7's four-step process at a lean
depth.

**Complexity signals** (PMBOK 11.4): risks interact with each other, or the
project needs a numeric estimate of overall cost or schedule exposure, not
just a qualitative Low/Medium/High rating; a funder or sponsor requires
quantitative risk reporting.

**Escalation:** add quantitative analysis (probability and impact scoring,
expected monetary value, or contingency reserves tied to specific risks,
per PMBOK 11.4 and Larson & Gray 7.7) only when a qualitative rating is no
longer sufficient to decide whether to act. Most projects using this
template will never need this.

## Procurement

**Lean default:** none. `project_definition.md`'s "External dependencies"
field is the only proxy.

**Complexity signals** (PMBOK Chapter 12, Larson & Gray Chapter 12): the
project contracts external vendors or subcontractors for meaningful work;
more than an informal purchase is involved; a contract has its own
deliverables, dates, or payment terms that need tracking.

**Escalation:** add a short vendor or contract register (vendor, scope,
contract reference, key dates, status) as project-specific structure in
`02_Work/` or `01_Planning/`, following the same identifier and single-
source-of-truth conventions as the rest of the repository. Do not build a
full procurement process for an informal purchase.

## Stakeholders

**Lean default:** `project_definition.md` Section 3 has a stakeholder
table (`STK-###`: interest or expectation, influence, engagement
approach), scoped to stakeholders who could materially affect the
project, not an exhaustive list.

**Complexity signals** (PMBOK Chapter 13, Larson & Gray 10.2): more than
one stakeholder group with different or conflicting interests; a
stakeholder whose support is not guaranteed; stakeholders outside the
immediate project team or client, such as regulators, the public, or other
internal departments.

**Escalation:** once a lean stakeholder register exists (name or role,
interest, influence, engagement approach), add a power-interest grid and a
distinct engagement plan per stakeholder group (PMBOK 13.2) once more than
a handful of stakeholders are involved or their interests genuinely
conflict.

## Integration

Integration is not a separate artifact to scale. It is the coherence of
everything above: `project_definition.md` acts as a lean charter,
`decision_log.md` acts as change control, and the reading order in
`README.md` Section 9 is what keeps a human or an AI agent able to
reconstruct the whole picture. As every other area scales, revisit
whether `project_definition.md` and `project_plan.md` still accurately
summarize the project; they are what keeps a more complex set of documents
integrated rather than fragmented.
