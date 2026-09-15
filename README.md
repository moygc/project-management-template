# Project Repository

> **Project:** `[Project Name]`. This repository is this project's management system, built on the Template_Projects structure. What the project is, why it exists, and its scope is defined in `00_Definition/project_definition.md`; that file is the authoritative source, not this paragraph. This README describes how the repository itself is organized and used, and applies the same way to every project built on this template.

## Purpose

This repository provides a simple, reusable system for managing projects.
It is designed to keep a project:

- clear and traceable;
- easy to navigate and continue;
- adaptable to different types of work;
- understandable by people and AI assistants.

The design follows a practical Pareto principle:

> Use the minimum structure that provides most of the control needed to define,
> plan, execute, monitor, deliver, and close a project.

The 80/20 principle is a design target, not a mathematical guarantee. Projects
with contractual, regulatory, financial, safety, or organizational requirements
may need additional controls.

---

# 1. Quick Start

If this repository was just cloned or copied to start a new project (that is, this is still the template), first follow the bootstrap procedure in `AGENTS.md`: rename the root folder, remove the template's `.git` history, and decide whether the new project needs its own version control. Then continue below.

Use the repository in this order:

1. Copy `04_Templates/project_definition.md` to
   `00_Definition/project_definition.md` and define the project. Replace the `[Project Name]` placeholder at the top of this README with the project's actual name.
2. Copy `04_Templates/decision_log.md` to `decision_log.md`.
3. Once the definition is sufficient, copy
   `04_Templates/project_plan.md` to `01_Planning/project_plan.md` and use
   `04_Templates/template_schedule.md` to create one authoritative schedule
   in `01_Planning/`.
4. Organize `02_Work/` according to the actual work packages and technical
   needs of the project.
5. Execute the work, maintain the schedule, and record significant decisions.
6. When a concise current snapshot is useful, copy
   `04_Templates/project_status.md` to `project_status.md`.
7. Place consolidated deliverables in `03_Outputs/`.
8. When formal acceptance, handover, pending commitments, or lessons need to
   be preserved, copy `04_Templates/project_closeout.md` to
   `project_closeout.md`.

Do not fill the files inside `04_Templates/` with project information. They
remain clean reference originals.

---

# 2. Repository Architecture

~~~text
Project_Name/
├── 00_Definition/
│   └── .gitkeep
├── 01_Planning/
│   └── .gitkeep
├── 02_Work/
│   └── README.md
├── 03_Outputs/
│   └── .gitkeep
├── 04_Templates/
│   ├── project_definition.md
│   ├── project_plan.md
│   ├── template_schedule.md
│   ├── decision_log.md
│   ├── project_status.md
│   └── project_closeout.md
├── .gitattributes
├── .gitignore
└── README.md
~~~

The `.gitkeep` files preserve intentionally empty folders in Git. Replace or
remove them naturally when the folders receive project content.

## Operational Locations

Each type of project information has one authoritative location:

| Template | Operational location | Use |
|---|---|---|
| `project_definition.md` | `00_Definition/project_definition.md` | Required project foundation |
| `project_plan.md` | `01_Planning/project_plan.md` | Required execution logic |
| `template_schedule.md` | `01_Planning/schedule.md` or `schedule.xlsx` | Specification for the required schedule |
| `decision_log.md` | `decision_log.md` | Required record of significant decisions |
| `project_status.md` | `project_status.md` | Optional current snapshot |
| `project_closeout.md` | `project_closeout.md` | Optional formal closure record |

The Markdown or Excel schedule must be declared as the single authoritative
schedule. Never maintain two competing schedules.

---

# 3. Management System

The repository follows the main project flow:

~~~text
DEFINITION → PLAN → SCHEDULE → WORK → OUTPUTS → CLOSEOUT
      │          │        │         │          │
      └──────────┴────────┴─────────┴──────────┤
                                               ▼
                                  DECISIONS AND STATUS
~~~

The core artifacts answer different management questions:

| Artifact | Main question | Default use |
|---|---|---|
| Project definition | What are we doing, why, and where does responsibility end? | Required |
| Project plan | How will the project be carried out? | Required |
| Operational schedule | What happens when, in what sequence, and who owns it? | Required |
| Decision log | What material decisions were made and why? | Required |
| Project status | Where are we now and what needs attention? | Conditional |
| Project closeout | What was achieved, accepted, transferred, or left open? | Conditional |

Git preserves how the project changed. The project artifacts preserve what the
project means and its current state.

---

# 4. Folder Responsibilities

## `00_Definition/`

Defines the need, purpose, expected value, objectives, scope, boundaries,
deliverables, material conditions, and success criteria.

> Define the project before planning how to execute it.

## `01_Planning/`

Translates the definition into an execution approach, work packages,
milestones, risks, responsibilities, and one operational schedule.

The plan describes execution logic. The schedule maintains activities, dates,
owners, status, and dependencies.

> Plan only to the level required to execute and control the work.

## `02_Work/`

Contains active sources, analyses, models, designs, drafts, code, calculations,
and intermediate results.

Its structure must follow the actual project. Do not create folders in advance
only because they appear in an example.

## `03_Outputs/`

Contains consolidated results and final deliverables.

~~~text
02_Work/    → material used to develop results
03_Outputs/ → consolidated results produced by the project
~~~

An output may be versioned when it is a project record or cannot be reliably
reconstructed. Reproducible generated outputs may be ignored.

## `04_Templates/`

Contains reusable reference originals. Operational copies become the
authoritative project records.

---

# 5. Information and Traceability

## Single Source of Truth

| Information | Authoritative location |
|---|---|
| Purpose, objectives, scope, deliverables, and success criteria | `00_Definition/project_definition.md` |
| Execution approach, work packages, milestones, and significant risks | `01_Planning/project_plan.md` |
| Activities, dates, dependencies, and operational status | Declared schedule in `01_Planning/` |
| Significant decisions and reasoning | `decision_log.md` |
| Current situational summary | `project_status.md`, when used |
| Active technical work | `02_Work/` |
| Consolidated deliverables | `03_Outputs/` |
| Acceptance, success evaluation, handover, and final commitments | `project_closeout.md`, when used |

Other files may reference or summarize this information, but must not create
competing editable sources.

## Identifier Convention

Identifiers connect related information without repeating descriptions:

| Prefix or term | Meaning | Format |
|---|---|---|
| `DEL` | Deliverable | `DEL-###` |
| `WP` | Work package | `WP-###` |
| `MS` | Milestone | `MS-###` |
| `ACT` | Activity | `ACT-###` |
| `RSK` | Risk or opportunity | `RSK-###` |
| `DEC` | Completed decision | `DEC-###` |
| `YYYY-MM-DD` | Calendar date | ISO 8601 |
| `—` | None or not applicable | Em dash |

Apply these rules:

1. Assign an identifier once and never reuse it.
2. Keep identifiers stable when descriptions change.
3. Reference identifiers instead of duplicating information.
4. Use three digits by default and allow gaps when an item is removed.
5. Define a new prefix here before using it systematically.

---

# 6. Planning and Control Rules

## Work Packages and Milestones

Each work package must have a clear purpose, owner, and relationship to a
deliverable or meaningful result.

Each milestone must represent an observable completion or decision point. When
timing matters, give it a target date, iteration, or triggering condition and
connect the relevant schedule activities to it.

## Schedule

Use one row per activity. Every activity must have:

- a stable activity ID;
- a work package;
- recognizable work;
- one accountable owner;
- planned timing or an equivalent completion condition;
- status;
- dependencies when applicable.

Keep approved baseline dates unchanged when they are needed for comparison.
Use forecast or actual fields only when they support a real control decision.

## Risks and Opportunities

Record uncertainties that could materially affect objectives, scope, schedule,
value, or deliverables. Do not list every imaginable risk.

## Decisions

Use the decision log for completed decisions that materially affect scope,
approach, assumptions, responsibilities, milestones, schedule, or technical
choices.

Pending decisions belong in the attention section of `project_status.md` until
they are decided.

## Status

The status document is a concise snapshot, not another task tracker. Detailed
activity status remains in the schedule.

Use it only when the schedule does not provide sufficient situational
awareness.

## Closeout

Formal closeout should confirm, as applicable:

- final outcome;
- deliverable acceptance;
- evaluation of the success criteria defined at initiation;
- evidence or location of results;
- handover and remaining commitments;
- essential lessons worth preserving.

---

# 7. Scaling the System

The stable core should remain small. Scale only the variable parts of the
repository.

Add a control or artifact only when:

1. it has a clear function;
2. that function is not already covered;
3. it supports execution, understanding, control, compliance, or delivery;
4. its value exceeds its maintenance cost.

Projects may require additional controls for budget, contracts, quality,
regulation, security, communications, stakeholders, suppliers, or formal
change approval. Add them only when the project context requires them.

Prefer:

- group before dividing;
- reference before duplicating;
- simplify before expanding;
- add complexity only when needed.

---

# 8. Version Control

Git is optional for projects created from this structure, but recommended when
history, collaboration, traceability, or recovery matters.

When this repository is used to start a new project, remove the template's `.git` history first and decide independently whether the new project needs its own version control. This bootstrap step is not part of the project's own history; follow the procedure in `AGENTS.md`.

## Source-First Principle

~~~text
SOURCE OR PROJECT RECORD → version
GENERATED AND REPRODUCIBLE → normally ignore
TEMPORARY OR LOCAL → ignore
SENSITIVE → never commit
~~~

Version files required to understand, continue, verify, or reconstruct the
project. File function matters more than file format. A spreadsheet, image,
PDF, or presentation may be an original project record.

Do not ignore `03_Outputs/` by default. Decide whether each output is a
reproducible build or a project record.

The `.gitignore` file excludes common temporary, local, generated, and
sensitive files. Add project-specific exclusions only when their purpose is
clear.

The `.gitattributes` file normalizes text line endings and protects common
binary formats from text conversion.

## Commit Convention

Use:

~~~text
type: short description
~~~

| Type | Use |
|---|---|
| `feat:` | Add meaningful project content |
| `fix:` | Correct content, data, logic, or inconsistency |
| `docs:` | Update documentation or guidance |
| `style:` | Change presentation without changing meaning |

Keep commits focused on meaningful units of work. Review changed files before
committing and do not intentionally commit temporary, generated, ignored, or
sensitive information.

~~~text
Complete meaningful work
        ↓
Review changed files
        ↓
Stage related files
        ↓
Commit
        ↓
Push when the shared history should be updated
~~~

Git, the decision log, and the status document have different functions:

| Record | Question answered |
|---|---|
| Git commit | What changed? |
| Decision log | What was decided and why? |
| Project status | Where are we now and what comes next? |

---

# 9. Using the Repository with AI

An AI assistant should reconstruct project context from the repository rather
than depend on previous conversations.

Recommended reading order:

~~~text
README.md
    ↓
00_Definition/project_definition.md
    ↓
01_Planning/project_plan.md
    ↓
Declared operational schedule
    ↓
project_status.md                 [if used]
    ↓
decision_log.md
    ↓
Relevant Work and Outputs
    ↓
project_closeout.md               [if used]
~~~

AI-specific instructions may define how an assistant should work. Project
documents remain the source of truth for what the project is and its current
state.

---

# 10. Repository Health Check

The repository is sufficiently organized when:

- every folder and artifact has a clear function;
- each type of information has one authoritative location;
- deliverables, work packages, milestones, activities, risks, and decisions
  can be connected through stable identifiers;
- sources are distinguishable from generated results;
- a person or AI assistant can locate the project context without prior
  conversation;
- unnecessary structure can be removed without losing clarity.

> The architecture should serve the project. The project should not serve the
> architecture.
