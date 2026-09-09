
# Project Repository

## Purpose

This repository provides a simple and reusable structure for managing projects.

It is designed to keep a project:

- clear;
- organized;
- traceable;
- easy to navigate;
- adaptable to different types of work;
- understandable by both people and AI assistants.

The architecture follows a simple principle:

> **Use the minimum structure required to keep the project clear and under control.**

The repository should provide approximately **80% of the required functionality
with 20% of the complexity**.

Do not add folders, documents, fields, or management processes unless they
solve a real project need.

---

# 1. Repository Architecture

```text
Project_Name/
├── 00_Definition/
│   └── .gitkeep
│
├── 01_Planning/
│   └── .gitkeep
│
├── 02_Work/
│   └── README.md
│
├── 03_Outputs/
│   └── .gitkeep
│
├── 04_Templates/
│   ├── project_definition.md
│   ├── project_plan.md
│   ├── template_schedule.md
│   ├── decision_log.md
│   └── project_status.md
│
├── .gitignore
└── README.md
```

This is the clean template-repository structure. When a project is initiated,
copy only the required templates to their operational locations. The templates
remain reference originals; the copied project documents become the project's
authoritative sources.

`04_Templates/template_schedule.md` is the format-neutral schedule
specification. Use it to create `01_Planning/schedule.md` by default or an Excel
schedule when explicitly requested. Never maintain both as competing sources.

The repository follows the main project flow:

**Definition → Planning → Work → Outputs**

Two transversal documents support this flow:

- `decision_log.md` preserves important project decisions;
- `project_status.md` provides a current project snapshot when needed.

---

# 2. Cognitive Architecture

The repository is not only a folder structure.

Each main artifact answers a different project question.

```text
                         PROJECT
                            │
                            ▼
                  PROJECT DEFINITION
                     What / Why?
                            │
                            ▼
                     PROJECT PLAN
                         How?
                            │
                            ▼
                       SCHEDULE
                     When / Who?
                            │
                            ▼
                         WORK
                       Execution
                            │
                            ▼
                        OUTPUTS
                         Results


                 ┌─────────────────────┐
                 │                     │
                 ▼                     ▼
           DECISION LOG          PROJECT STATUS
        What was decided?        Where are we?
              Why?                 What next?
```

Together, these artifacts provide the minimum information required to
understand and manage the project.

---

# 3. `00_Definition/`

## Purpose

Defines the project before detailed planning begins.

It answers:

> **What are we doing and why?**

Main artifact:

```text
00_Definition/
└── project_definition.md
```

`project_definition.md` establishes the project foundation, including:

- context;
- problem or need;
- purpose and expected value;
- objectives;
- scope and boundaries;
- main deliverables;
- requirements and constraints;
- success criteria.

The definition should remain relatively stable.

If an important decision changes the project definition, update the relevant
section and record the decision in `decision_log.md`.

### Rule

> **Define the project before planning how to execute it.**

---

# 4. `01_Planning/`

## Purpose

Translates the project definition into an executable approach.

It answers:

> **How will the project be carried out?**

Typical structure:

```text
01_Planning/
├── project_plan.md
└── schedule.md
```

## `project_plan.md`

Defines the execution logic of the project.

It normally includes:

- execution approach;
- work packages;
- milestones;
- roles and responsibilities;
- significant risks;
- monitoring and control.

It should describe the structure of the work without reproducing the detailed
activity schedule.

## `schedule.md`

Contains the operational schedule and defines how it should be maintained.

It normally tracks:

- activities;
- work packages;
- responsibilities;
- start and end dates;
- status;
- dependencies.

### Rule

> **Plan the work at the level necessary to execute and control it.**

Do not create detailed planning information that does not support execution
or decision-making.

---

# 5. `02_Work/`

## Purpose

Contains the active work required to produce project results.

It answers:

> **Where is the project work developed?**

Unlike Definition and Planning, this folder does not have a universal internal
structure.

Its organization should reflect the actual nature of the project.

For example, an engineering project could use:

```text
02_Work/
├── Data/
├── Design/
├── Modeling/
└── Evaluation/
```

A research project could use:

```text
02_Work/
├── Literature/
├── Methodology/
├── Data/
└── Analysis/
```

A software project could use:

```text
02_Work/
├── Requirements/
├── Development/
└── Testing/
```

A small project may not require subfolders at all:

```text
02_Work/
├── analysis.xlsx
├── notes.md
└── draft.md
```

Typical content includes:

- data;
- calculations;
- analyses;
- models;
- designs;
- working documents;
- drafts;
- intermediate results.

### Rule

> **Adapt Work to the project instead of forcing the project into a predefined structure.**

Create a subfolder only when it represents a meaningful and recurring block
of work.

---

# 6. `03_Outputs/`

## Purpose

Contains consolidated project results and final deliverables.

It answers:

> **What did the project produce?**

For a simple project:

```text
03_Outputs/
└── final_report.pdf
```

For a project with several types of outputs:

```text
03_Outputs/
├── Reports/
├── Models/
└── Presentations/
```

The exact structure depends on the project.

### Work vs. Outputs

Use this distinction:

```text
02_Work/     → material used to develop the results
03_Outputs/  → consolidated results produced by the project
```

Drafts and active analyses normally belong in `02_Work/`.

Final or formally consolidated results belong in `03_Outputs/`.

### Rule

> **Outputs contain results, not the process used to create them.**

---

# 7. `decision_log.md`

## Purpose

Preserves the memory of significant project decisions.

It answers:

> **What was decided and why?**

Use it for decisions that materially affect:

- scope;
- execution approach;
- important assumptions;
- system configuration;
- major technical choices;
- milestones;
- responsibilities;
- relevant project conditions.

Do not use it as meeting minutes or as a record of routine actions.

Detailed evidence and analysis should remain in their corresponding project
files.

### Rule

> **Record decisions that would cause confusion or rework if their reasoning
> were forgotten.**

When a previous decision changes, create a new decision entry rather than
removing the historical record.

---

# 8. `project_status.md`

## Purpose

Provides a concise snapshot of the current project state.

It answers:

> **Where are we now, what requires attention, and what comes next?**

This artifact is optional.

Use it when the project becomes sufficiently long, complex, or collaborative
that the schedule alone no longer provides enough situational awareness.

It may summarize:

- current project phase;
- overall status;
- meaningful progress;
- current blockers or issues;
- immediate next steps;
- next checkpoint.

`project_status.md` should not become another tracking system.

The detailed operational status remains in the schedule.

### Rule

> **Use Project Status for situational awareness, not activity-level control.**

For small projects, the schedule may be sufficient and this file can be omitted.

---

# 9. `README.md`

## Purpose

Explains how the repository works.

It answers:

> **How should this project repository be understood and used?**

The README describes:

- repository architecture;
- function of each folder;
- relationship between core artifacts;
- general organization rules.

It should not duplicate the detailed instructions contained in individual
templates or project documents.

### Rule

> **README explains the system; project artifacts contain the project information.**

---

# 10. Project Core

The minimum project management system is built around four core artifacts:

| Artifact | Main Question |
|---|---|
| `project_definition.md` | What are we doing and why? |
| `project_plan.md` | How will we do it? |
| `schedule.md` | What happens when and who is responsible? |
| `decision_log.md` | What important decisions were made and why? |

An optional fifth artifact provides situational awareness:

| Artifact | Main Question |
|---|---|
| `project_status.md` | Where are we now and what comes next? |

This core remains stable across different types of projects.

The technical or domain-specific artifacts change according to the project.

---

# 11. Information Flow

Information should move through the repository according to its function:

```text
PROJECT DEFINITION
        │
        │ defines
        ▼
PROJECT PLAN
        │
        │ organizes
        ▼
SCHEDULE
        │
        │ coordinates
        ▼
WORK
        │
        │ produces
        ▼
OUTPUTS
```

Throughout the project:

```text
DECISIONS ──────────────► decision_log.md

CURRENT STATE ──────────► project_status.md
                           when required
```

The documents should support each other without becoming duplicate sources
of the same information.

---

# 12. Single Source of Truth

Each type of information should have one primary location.

Examples:

| Information | Primary Location |
|---|---|
| Project purpose and scope | `project_definition.md` |
| Execution approach | `project_plan.md` |
| Detailed activities and dates | The declared operational schedule: `schedule.md` or `schedule.xlsx` |
| Current situational summary | `project_status.md` |
| Significant decisions and reasoning | `decision_log.md` |
| Active technical work | `02_Work/` |
| Consolidated results | `03_Outputs/` |

Other documents may reference or summarize this information when necessary,
but they should not create competing versions of the same source.

## Identifier and Abbreviation Convention

Identifiers connect related information without repeating its description.
Use the following convention wherever these elements appear:

| Prefix / Term | Meaning | Format | Example |
|---|---|---|---|
| `ID` | Identifier | Stable and unique within its element type | — |
| `WP` | Work Package | `WP-###` | `WP-001` |
| `MS` | Milestone | `MS-###` | `MS-001` |
| `ACT` | Activity | `ACT-###` | `ACT-001` |
| `DEC` | Decision | `DEC-###` | `DEC-001` |
| `YYYY-MM-DD` | Calendar date | ISO 8601 year-month-day | `2026-09-08` |
| `—` | None or not applicable | Em dash | — |

Apply these rules:

1. Assign an identifier once and never reuse it for another element.
2. Keep identifiers stable even when names or descriptions change.
3. Reference the identifier instead of copying information between documents.
4. Use three digits by default and allow gaps when an element is removed.
5. Define any new prefix in this section before using it in a template.

---

# 13. Project Lifecycle

The repository can support the complete project lifecycle:

```text
INITIATION
    │
    ├── Understand the need
    ├── Define the project
    │
    ▼
PLANNING
    │
    ├── Define execution approach
    ├── Structure work
    ├── Build schedule
    │
    ▼
EXECUTION
    │
    ├── Perform work
    ├── Monitor progress
    ├── Record significant decisions
    │
    ▼
CLOSING
    │
    ├── Consolidate outputs
    ├── Confirm completion
    └── Capture relevant final knowledge
```

The folder architecture and the project lifecycle are related but are not
the same thing.

Folders organize information by function.

The lifecycle describes how the project progresses over time.

---

# 14. Scaling the Repository

The architecture should scale with the project.

## Small Project

```text
Project_Name/
├── 00_Definition/
│   └── project_definition.md
├── 01_Planning/
│   ├── project_plan.md
│   └── schedule.md
├── 02_Work/
├── 03_Outputs/
├── decision_log.md
└── README.md
```

## Larger Project

The same core remains, but `02_Work/` and `03_Outputs/` may grow according
to real project needs.

Additional artifacts should be created only when they solve a specific
management, technical, regulatory, communication, or traceability need.

### Rule

> **Scale the variable parts of the repository, not the core unnecessarily.**

---

# 15. Version Control

This repository can be versioned with Git to preserve the history of
meaningful project changes.

Git is optional and does not change the repository architecture.

## Source-First Principle

The repository follows a **source-first** approach.

Git should preserve the files required to understand, continue, verify, or
reconstruct the project.

The decision to version a file should therefore depend on its **function in the
project**, not only on its file format.

Use the following general rule:

```text
SOURCE / PROJECT RECORD    → version
GENERATED / REPRODUCIBLE   → ignore
TEMPORARY                  → ignore
LOCAL                      → ignore
SENSITIVE                  → never commit
```

### Source and Project Records

Version files that contain original project information, meaningful project
state, or information required to continue the work.

Examples may include:

- `.md`, `.txt`, `.tex`, and other authored source files;
- source code and scripts;
- configuration files;
- project data;
- calculations and models;
- spreadsheets containing original project information;
- source images, diagrams, or photographs;
- planning and management artifacts;
- final deliverables when they represent project records rather than
  reproducible builds.

A binary file is not automatically a generated artifact.

For example:

```text
02_Work/raw_data.xlsx
02_Work/economic_model.xlsx
02_Work/experimental_photo.jpg
03_Outputs/final_model.xlsx
```

may contain original or necessary project information and should therefore be
versioned when appropriate.

### Generated and Reproducible Files

Files that can be reliably reconstructed from versioned sources should normally
be excluded from Git.

For example:

```text
data.csv + analysis.py → generated_plot.png
source.md + build.py   → generated_report.pdf
```

When the complete source and generation process are versioned, the generated
artifact does not normally need to be part of the Git history.

The general principle is:

> **Version the source or project record, not unnecessary reconstruction.**

Do not ignore complete file formats globally when those formats may also
contain legitimate project sources.

For example, avoid general rules such as:

```text
*.pdf
*.docx
*.xlsx
*.pptx
*.png
*.jpg
```

because the same formats may represent either original project information or
generated artifacts.

Use `.gitignore` to exclude files according to their role in the project.

### Outputs

`03_Outputs/` should not be ignored by default.

This directory contains consolidated project results and final deliverables,
which may represent important project records.

Some outputs may be reproducible and therefore ignored, while others may need
to be preserved in Git.

Decide according to the nature of each output:

```text
reproducible output     → normally ignore

project record or
non-reproducible output → normally version
```

### Sensitive Information

Sensitive information should never be committed to Git.

Examples may include:

- passwords;
- API keys;
- access tokens;
- credentials;
- private environment variables;
- confidential files that are not authorized for repository storage.

Sensitive configuration should be stored outside the repository or through an
appropriate secrets-management mechanism.

Files such as `.env` should normally be excluded through `.gitignore` when they
contain local or sensitive values.

---

## Commit Convention

Commits should create a simple and readable history of meaningful project
changes.

This repository uses a minimal convention inspired by Conventional Commits
and adapted to project and document repositories.

Use:

```text
type: short description
```

Use four commit types by default:

| Type | Use when... | Example |
|---|---|---|
| `feat:` | Adding meaningful new project content | `feat: add conceptual system boundaries` |
| `fix:` | Correcting existing content, data, logic, or inconsistencies | `fix: correct biomass origin` |
| `docs:` | Updating repository documentation, instructions, or guidance | `docs: update README version control rules` |
| `style:` | Changing formatting or presentation without changing meaning | `style: improve LaTeX report formatting` |

Choose the type according to the main purpose of the change:

```text
New meaningful content?
       │
       Yes ──→ feat:
       │
       No
       ▼
Correction?
       │
       Yes ──→ fix:
       │
       No
       ▼
Documentation or instructions?
       │
       Yes ──→ docs:
       │
       No
       ▼
Formatting only?
       │
       Yes ──→ style:
```

If more than one type could apply, use the one that best represents the
main purpose of the commit.

Do not create additional commit types unless a recurring project need
justifies them.

---

## Commit Rules

1. Commit when a meaningful unit of work is completed.
2. Keep each commit focused on one main change.
3. Describe clearly what changed.
4. Prefer small, meaningful commits over large commits with unrelated changes.
5. Review changed files before committing.
6. Do not intentionally commit temporary, generated, ignored, or sensitive files.
7. Do not commit every minor edit; commit when the change represents meaningful progress.

The objective is not to create a perfect Git history, but to make project
evolution understandable.

---

## Commit Workflow

For individual work, use:

```text
WORK
  │
  ▼
Complete a meaningful change
  │
  ▼
Review changed files
  │
  ▼
Stage related files
  │
  ▼
Commit using the appropriate type
  │
  ▼
Continue working
```

Keep this workflow simple unless collaboration or project complexity
requires additional Git practices.

---

## Git and Project Records

Git and project artifacts have different functions:

```text
Git commit
    └── What changed?

decision_log.md
    └── What important decision was made and why?

project_status.md
    └── Where is the project now and what comes next?
```

Do not use commit messages as a substitute for the decision log.

> **Git preserves project evolution; project artifacts preserve project meaning and state.**

---

# 16. Rules for Adding Structure

Before creating a new folder, document, table, field, or management artifact,
ask:

1. Does it have a clear function?
2. Does that function already exist somewhere else?
3. Will it help execute, understand, control, or deliver the project?
4. Is the expected value greater than the complexity of maintaining it?

If the answer is not clearly yes, do not add it yet.

Prefer:

**group before dividing**

**reference before duplicating**

**simplify before expanding**

**add complexity only when needed**

---

# 17. Using the Repository with AI

The architecture is designed so that an AI assistant can reconstruct the
essential project context without depending on previous conversations.

A recommended reading order is:

```text
README.md
    │
    ▼
project_definition.md
    │
    ▼
project_plan.md
    │
    ▼
project_status.md        [if used]
    │
    ▼
decision_log.md
    │
    ▼
Relevant Work / Outputs
```

This allows the assistant to understand:

1. how the repository works;
2. what the project is;
3. how it should be executed;
4. where the project currently stands;
5. what important decisions have already been made;
6. which technical information is relevant to the current task.

AI-specific instructions may exist separately when required.

They should define **how the assistant should work**, while the project
documents remain the source of truth for **what the project is and its
current state**.

---

# 18. Final Principle

The repository should remain as simple as possible while preserving:

- clarity;
- traceability;
- continuity;
- control;
- adaptability.

The stable core provides the project map:

```text
Definition → Plan → Schedule → Work → Outputs
```

The transversal artifacts preserve context:

```text
Decisions + Status
```

Git may preserve the evolution of these artifacts when version control is
required.

Everything else should emerge from the real needs of the project.

> **The architecture should serve the project. The project should not serve
> the architecture.**


