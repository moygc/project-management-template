# Project Schedule Template

## Purpose

Define the minimum structure and rules for creating and maintaining the
operational project schedule.

Use this template to create:

- `01_Planning/schedule.md` by default; or
- `01_Planning/schedule.xlsx` when a spreadsheet is explicitly requested or
  provides clear operational value.

This template is a specification, not the active schedule.

## Source-of-Truth Rule

A project must have only one authoritative operational schedule.

If both Markdown and Excel representations exist, identify which file is
authoritative. The other must be generated or read-only and must not be
maintained independently.

## Minimum Schedule Structure

Use one row for each activity. Relate every activity to a work package defined
in `project_plan.md`.

| Activity ID | Work Package ID | Activity | Owner | Planned Start | Planned Finish | Status | Depends On |
|---|---|---|---|---|---|---|---|
| ACT-001 | WP-001 | [Specific work] | [Person / role] | YYYY-MM-DD | YYYY-MM-DD | Not Started | — |
| ACT-002 | WP-001 | [Specific work] | [Person / role] | YYYY-MM-DD | YYYY-MM-DD | In Progress | ACT-001 |
| ACT-003 | WP-002 | [Specific work] | [Person / role] | YYYY-MM-DD | YYYY-MM-DD | Completed | ACT-002 |

Identifiers and abbreviations follow the convention defined in `README.md`.

## Field Rules

- **Activity ID:** Stable activity identifier using the `ACT-###` convention.
- **Work Package ID:** Reference to a work package using `WP-###`.
- **Activity:** Specific work with a recognizable completion condition.
- **Owner:** One person or role accountable for moving the activity forward.
- **Planned Start:** Approved start date using `YYYY-MM-DD`.
- **Planned Finish:** Approved completion date using `YYYY-MM-DD`.
- **Status:** `Not Started`, `In Progress`, `Blocked`, `Completed`, or
  `Cancelled`.
- **Depends On:** Activity ID that must precede or condition the activity. Use
  `—` when no dependency exists and commas for multiple dependencies.

## Optional Extensions

Add a column only when it supports a real planning or control decision.
Possible extensions include:

- iteration or cycle;
- actual start;
- forecast finish;
- actual finish;
- priority;
- progress;
- variance or notes.

Projects using iterative or adaptive delivery may replace dates with an
iteration, milestone, or explicit completion condition when calendar dates do
not provide useful control.

## Excel Generation Rules

When an Excel schedule is requested:

1. Create `01_Planning/schedule.xlsx` from this schema.
2. Use one worksheet named `Schedule` unless another sheet has a justified
   purpose.
3. Preserve the minimum columns and identifier conventions.
4. Use one activity per row, a single header row, filters, and frozen headers.
5. Store dates as dates and display them as `YYYY-MM-DD`.
6. Do not use merged cells or color as the only carrier of information.
7. Add validation or formulas only when they materially improve control.

## Usage Rules

- Keep planned dates unchanged when they serve as an approved baseline.
- Record meaningful deviations using optional forecast or actual fields.
- Update the schedule when project state changes, not merely to create the
  appearance of activity.
- Do not duplicate detailed schedule information in `project_status.md`.
- Preserve cancelled activities when their history remains relevant.

The schedule is sufficient when it makes sequence, ownership, current state,
and dependencies clear.
