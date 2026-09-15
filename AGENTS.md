# AGENTS.md

## Purpose

This file is the entry point for any AI agent working in this repository,
whether the work is still on the template itself or on a project already
bootstrapped from it. Read it before making changes.

## 1. Identify the State of This Repository

Check first whether this repository is:

- **The template itself**, as cloned from GitHub: `.git` present, pointing to
  the template's own remote, `04_Templates/` populated, and
  `00_Definition/`, `01_Planning/`, `03_Outputs/` still empty.
- **An already-bootstrapped project**: root folder renamed to the project
  name, `.git` reinitialized (or absent), and operational files present in
  `00_Definition/`, `01_Planning/`, or later stages.

  If this is the case, this project's own identity, purpose, and scope live in `00_Definition/project_definition.md`, not in this file or in `README.md`. See Section 3 below before doing any project-specific work.

Do not edit files inside `04_Templates/` in either case. They remain clean
reference originals; operational copies are made elsewhere, per
`README.md` Section 1.

## 2. Bootstrapping a New Project

Do this once, only when starting a new project from the template.

1. Clone or copy this repository into the new project's location, and rename
   the root folder to the actual project name.
2. Record the template's origin before removing its git history: inside the
   cloned folder, run `git rev-parse --short HEAD` to get the current commit
   hash, and write that hash plus today's date into the `**Project:**` line
   at the top of `README.md` (for example: `Bootstrapped from
   Template_Projects commit abc1234 on 2026-09-15`). This is the only trace
   of which template version the project started from, since the next step
   deletes the git history that would otherwise show it. If the repository
   was copied without git (for example, a downloaded ZIP, with no `.git`
   folder present), get the same short commit hash directly from the
   GitHub repository page instead, from the latest commit on its default
   branch, and use it the same way.
3. Remove the cloned git history: delete the `.git` folder entirely
   (`rm -rf .git` on Linux or macOS; delete it via the file manager on
   Windows, or `rmdir /s /q .git` from PowerShell). This repository must
   never inherit the template's commit history, and must never push to the
   template's original remote.
4. Decide whether this project needs its own version control. Use the rule
   already defined in `README.md` Section 8: git is optional, recommended
   when history, collaboration, traceability, or recovery matters.
   - If yes: run `git init`, make a first commit
     (`chore: initialize project from Template_Projects`), and separately
     decide whether it needs a remote now (a new, independent repository,
     usually private) or can stay local-only until that need appears.
   - If no: skip git initialization. Once `project_definition.md` or
     `decision_log.md` exist, record that this project intentionally has no
     version control, so the choice stays traceable.
5. Continue with the Quick Start in `README.md` Section 1.

## 3. Working in an Already-Bootstrapped Project

Follow the reading order in `README.md` Section 9 (Using the Repository with
AI) to reconstruct project context before doing any work.

When the project's actual situation (its scope, budget, stakeholders, or the work itself) looks more complex than the lean default template assumes, consult `SCALING.md` before proposing or building new structure. It gives the concrete complexity signals and the exact escalation for each project management area, grounded in standard references, so scaling decisions are not improvised.

Follow the single-source-of-truth table in `README.md` Section 5. Never
create a second editable copy of information that already has an
authoritative location.

Never remove the instructional guidance (`Purpose`, `Usage Rules`, checklists) from an operational document once it is filled, even to shorten it. It stays permanently, per `README.md` Section 4.

Do not translate the structure of these documents (headers, field names, rules) on your own initiative, even when the user works in another language; the content you fill in always follows the user's language without needing to ask. If the user explicitly asks you to translate the templates or an operational document's format into another language, do it, keeping the identifier codes (`DEL`, `STK`, `WP`, `MS`, `ACT`, `RSK`, `DEC`) untranslated. See `README.md` Section "Language".

## 4. Commit Discipline

Once a project has its own git repository:

- Use the commit types defined in `README.md` Section 8
  (`feat:`, `fix:`, `docs:`, `style:`, `chore:`).
- Check the current state of the working tree before staging or committing,
  so unrelated or uncommitted work is never swept into the wrong commit.
- Never commit project-specific content into `04_Templates/`; those files
  stay clean.
