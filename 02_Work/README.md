# Work Area

## Purpose

This directory contains the active work required to produce the project
deliverables.

Its structure must be designed from the project definition and project plan.
Do not create folders in advance merely because they appear in an example.

## Core Rules

- Use one authoritative location for each piece of information.
- Reference existing information instead of copying it.
- Group related work before creating additional folders.
- Create a folder only when it represents a meaningful and recurring block of
  work.
- Keep the structure as shallow as practical.
- Do not use ambiguous folders such as `Misc/`, `General/`, or `Other/`.
- Keep active sources and intermediate work here.
- Place consolidated deliverables in `03_Outputs/`.

Generated reports may reproduce source information, but they must not become a
second editable source. The versioned source remains authoritative and the
generated result should be reproducible from it.

## Designing the Work Structure

Before creating folders:

1. Read `README.md`, the project definition, and the project plan.
2. Identify the real work packages, information sources, transformations, and
   intermediate results.
3. Propose the smallest structure that makes those elements easy to locate.
4. Verify that every proposed folder has one clear purpose and does not
   duplicate or disperse information.
5. Create the structure only after it is accepted by the project lead.
6. Adjust it only when the current structure no longer supports the work.

## Reference Architectures

These are starting patterns, not mandatory structures. Select and combine only
the elements justified by the project.

| Project Type | Possible Initial Structure |
|---|---|
| Research | `Literature/`, `Methodology/`, `Data/`, `Analysis/` |
| Software | `src/`, `tests/`, `docs/`, `scripts/` |
| Data or modeling | `data/`, `notebooks/`, `src/`, `models/` |
| Design | `Research/`, `Concepts/`, `Design/`, `Validation/` |
| Engineering | `Requirements/`, `Calculations/`, `Design/`, `Verification/` |
| Documentation | `Sources/`, `Drafts/`, `Assets/`, `Reviews/` |

Code, scripts, notebooks, data, models, and their required configurations
should be versioned when they are necessary to understand, continue, verify,
or reproduce the work.

## Architecture Check

Before approving the structure, confirm:

- [ ] Does every folder support real project work?
- [ ] Is every piece of information stored in one authoritative location?
- [ ] Can a person or AI assistant locate information without prior context?
- [ ] Are source materials distinguishable from generated results?
- [ ] Can any folder or level be removed without losing clarity?

If the structure passes these checks, it is sufficiently organized.
