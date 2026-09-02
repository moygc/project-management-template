# Project Schedule

The operational project schedule is maintained in an Excel file.

This document defines the minimum structure and rules for organizing it.

## Schedule Structure

Use one row for each activity and organize activities according to the work packages defined in `project_plan.md`.

| ID | Work Package | Activity | Responsible | Start | End | Status | Dependency |
|---|---|---|---|---|---|---|---|
| A1 | WP1 | [Activity] | [Person / Role] | YYYY-MM-DD | YYYY-MM-DD | Not Started | — |
| A2 | WP1 | [Activity] | [Person / Role] | YYYY-MM-DD | YYYY-MM-DD | In Progress | A1 |
| A3 | WP2 | [Activity] | [Person / Role] | YYYY-MM-DD | YYYY-MM-DD | Completed | A2 |

## Field Rules

- **ID:** Unique activity identifier.
- **Work Package:** Work package defined in `project_plan.md`.
- **Activity:** Specific work to be performed.
- **Responsible:** Person or role accountable for the activity.
- **Start:** Planned start date.
- **End:** Planned completion date.
- **Status:** `Not Started`, `In Progress`, `Completed`, or `Blocked`.
- **Dependency:** ID of an activity that must precede or condition this activity.

## Usage

Keep the schedule simple and operational.

Update it during project execution to reflect current status while preserving the planned dates as the project baseline when schedule control is required.

Additional columns should only be added when they provide information that is necessary for planning or controlling the project.