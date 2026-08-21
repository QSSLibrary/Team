# PR Workflow for Outside Collaborators

> A practical, step-by-step guide to contributing to
> the `QSSLibrary/Team` repository as an **outside
> collaborator** — someone who doesn't have direct
> write access to the repository.
>
> This document is **committed** (not a working note)
> and is intended to be visible to all contributors,
> including first-time contributors.
>
> For related information, see:
> - `BRANCH-NAMING.md` — how to name your branches
> - `CONTRIBUTING.md` — overall contribution
>   workflow and policies
> - `CODE_OF_CONDUCT.md` — community standards
> - `.github/PULL_REQUEST_TEMPLATE/` — the PR body
>   templates

---

## 1. The mental model

GitHub has **two kinds of places** for any open-
source project:

- The **canonical repository** — the project's
  official home. For QSSL, this is
  `QSSLibrary/Team` (and the rest of the
  `QSSLibrary` organization). Most contributors
  **cannot push directly** to this repository.
- **Your fork** — a personal copy of the canonical
  repository that lives under **your own GitHub
  username**. You have **full write access** to
  your fork.

A **Pull Request (PR)** is a request to move a
branch from one place (typically your fork) to
another (typically the canonical repository's main
branch). The project's maintainers review the PR
and either merge it, request changes, or close it.

So the typical flow is:

```
edit files in your local clone
  → commit on a branch
    → push to your fork
      → open a PR from your fork to the canonical repo
        → maintainers review
          → merge
            → your branch is auto-deleted
```

The rest of this document walks through each step.

## 2. The two-step setup (one-time per machine)

Before you can open a PR, you need to:

1. **Fork** the repository on GitHub
2. **Clone** your fork locally

### 2.1 Fork on GitHub

1. Open `https://github.com/QSSLibrary/Team` in
   your browser.
2. Click the **Fork** button in the top-right
   corner.
3. GitHub creates a copy at
   `https://github.com/<your-username>/Team`.
4. You now have full write access to *your* fork.
   You still **cannot push** to `QSSLibrary/Team`
   directly.

### 2.2 Clone your fork locally

In your terminal:

```bash
git clone https://github.com/<your-username>/Team.git
cd Team
```

Replace `<your-username>` with your actual GitHub
username.

### 2.3 Add the canonical repo as a remote

This step lets you sync your fork with the
canonical repository periodically. One-time setup:

```bash
git remote add upstream https://github.com/QSSLibrary/Team.git
git remote -v
```

You should see two remotes: `origin` (your fork)
and `upstream` (the canonical repo).

## 3. Sync your fork with the canonical repo (per work item)

Before you start any new piece of work, sync your
fork's `main` branch with the canonical repo:

```bash
git checkout main
git fetch upstream
git merge upstream/main
git push origin main
```

This ensures your fork has the latest content. **Do
this every time you start a new branch.**

## 4. Create a branch with a convention-compliant name

Branch names in this repository follow
`BRANCH-NAMING.md`. Briefly:

| Prefix | Use for | Example |
|---|---|---|
| `wg/<name>` | New working-group proposal | `wg/celestial-mechanics` |
| `gov/<name>` | Governance document change | `gov/charter-amendment-v2` |
| `std/<name>` | Standard, policy, or guideline change | `std/cpp-style-update` |
| `decisions/<name>` | ADR / decision record | `decisions/adr-001-cpp20` |
| `joint/<name>` | Joint WG proposal (cross-WG) | `joint/spherical-astronomy` |
| `topic/<name>` | Anything else | `topic/fix-typo` |

Create the branch:

```bash
git checkout -b wg/celestial-mechanics
```

## 5. Make changes and commit

Edit files as needed. When you're ready to commit:

```bash
git add .
git commit -s -m "Add Celestial Mechanics WG proposal

This proposal establishes a working group for
celestial mechanics primitives and orbital
dynamics.

Co-Authored-By: Your Name <you@example.com>"
```

**The `-s` flag is important.** It adds a
`Signed-off-by:` line that the DCO (Developer
Certificate of Origin) requires. Every commit
must have this line. See
`policies/licensing-and-cla.md` for the DCO
details.

## 6. Push to your fork

```bash
git push origin wg/celestial-mechanics
```

After this, your fork on GitHub has the new branch.

## 7. Open the PR

Go to one of these URLs in your browser:

**For a specific PR template** (recommended):

```
https://github.com/QSSLibrary/Team/compare/main...<your-username>:<branch>?template=<template-name>.md
```

**For the default PR template** (no `?template=`):

```
https://github.com/QSSLibrary/Team/compare/main...<your-username>:<branch>
```

### 7.1 Examples

- New working-group proposal on
  `wg/celestial-mechanics`:
  ```
  https://github.com/QSSLibrary/Team/compare/main...<your-username>:wg/celestial-mechanics?template=wg-proposal.md
  ```
- Governance change on `gov/charter-amendment-v2`:
  ```
  https://github.com/QSSLibrary/Team/compare/main...<your-username>:gov/charter-amendment-v2?template=governance.md
  ```
- Joint proposal on `joint/spherical-astronomy`:
  ```
  https://github.com/QSSLibrary/Team/compare/main...<your-username>:joint/spherical-astronomy?template=joint-proposal.md
  ```
- Topic (typo fix) on `topic/fix-typo`:
  ```
  https://github.com/QSSLibrary/Team/compare/main...<your-username>:topic/fix-typo
  ```

### 7.2 URL syntax breakdown

The `main...<your-username>:<branch>` part is
GitHub's standard cross-fork compare syntax:

- `main` = the **base** branch on the canonical
  repo (the one you want your changes to go into)
- `...` (three dots) = "compare against"
- `<your-username>:<branch>` = the **head** branch
  on your fork (the one with your changes)

GitHub looks up `<template-name>.md` in
`.github/PULL_REQUEST_TEMPLATE/` of the **base**
repository and pre-fills the PR body with its
contents.

## 8. The PR is open — what happens next?

Once you open the PR, the project lead, TSC, or
designated reviewers will be notified. The typical
flow:

1. **CI checks** run automatically (when CI is
   configured). Make sure all checks pass.
2. **Reviewer(s)** read the PR, leave comments,
   and either:
   - **Approve** — the PR is good to merge
   - **Request changes** — the PR needs revisions
   - **Comment** — discussion without formal
     approval/rejection
3. **You respond** to comments by:
   - **Pushing new commits** to your branch (the
     PR updates automatically)
   - **Commenting** to clarify or discuss
   - **Resolving threads** when addressed
4. **Maintainer merges** the PR. The merge may
   squash your commits, rebase them, or use a
   merge commit — the maintainer decides per
   `standards/git-workflow.md` (a Phase 2 doc).
5. **Your branch is auto-deleted** (configured at
   the repo level). You can re-create the branch
   from the latest `main` if you have more work.

## 9. After the PR is merged

- Your fork's `main` branch is now behind the
  canonical `main` again. Sync your fork per §3.
- The branch you used for the PR is auto-deleted
  on GitHub (you can also delete the local
  reference: `git branch -d wg/celestial-mechanics`).
- For a major change (e.g., a charter amendment or
  ADR), an entry may be added to the relevant
  document's decision log per
  `governance/evolution.md` §6.2.

## 10. What you can and can't do

As an outside collaborator (no write access to
`QSSLibrary/Team`):

| Action | Allowed? |
|---|---|
| Fork the repository | ✅ Yes |
| Push to your fork | ✅ Yes |
| Open a PR to `QSSLibrary/Team` | ✅ Yes |
| Push directly to `QSSLibrary/Team` | ❌ No |
| Review your own PR | ⚠️ Allowed, but you can't be the only reviewer |
| Approve your own PR | ❌ No (GitHub enforces this) |
| Merge your own PR | ❌ No (only maintainers can merge) |
| Close your own PR | ✅ Yes |
| Reopen your own PR | ✅ Yes |
| Comment on others' PRs | ✅ Yes |
| Approve others' PRs | ❌ No (you need to be a maintainer) |

## 11. Common pitfalls and how to avoid them

### 11.1 You forgot to sign off your commits

The DCO check (when configured) will fail. Fix:

```bash
# Sign off the most recent commit
git commit --amend --signoff --no-edit
# Or, for multiple commits
git rebase --exec 'git commit --amend --no-edit --signoff' HEAD~3
git push --force-with-lease origin <branch>
```

### 11.2 Your fork is behind upstream

You'll see merge conflicts or your PR will be
"out of date." Fix:

```bash
git checkout main
git fetch upstream
git merge upstream/main
git push origin main
git checkout <your-branch>
git merge main    # or rebase, depending on project policy
git push --force-with-lease origin <your-branch>
```

### 11.3 You committed to `main` instead of a branch

This is common when you forget to create a branch
first. Recover by moving the commit to a new
branch:

```bash
git checkout main
git pull
git checkout -b <correct-branch-name>
git push origin <correct-branch-name>
```

Then open a PR from the new branch. The commit
that was on `main` is now on the new branch.

### 11.4 You used the wrong branch name prefix

You can rename the branch:

```bash
git branch -m <old-name> <new-name>
git push origin :<old-name> <new-name>
```

Then update any open PRs to point at the renamed
branch (GitHub usually handles this automatically
when you push the renamed branch).

### 11.5 Your PR is too large

Large PRs are hard to review. The convention in
this project is:

- **Small PRs preferred.** Aim for <300 lines of
  changes per PR.
- **Split large changes** into multiple PRs by
  feature, file, or concern.
- **Use draft PRs** (`?draft=true` in the URL, or
  the "Create draft pull request" option on the
  PR creation form) for work-in-progress that
  isn't ready for review.

### 11.6 You don't know which PR template to use

Use the default. You can also look at the
**Compare** page when you open a PR — GitHub
shows a dropdown of available templates. If
unsure, the project lead will help you re-target.

## 12. A worked example

Let's say you want to propose a new working group
for celestial mechanics. Step by step:

```bash
# (one-time per machine)
# 1. Fork on GitHub: click "Fork" at
#    https://github.com/QSSLibrary/Team

# 2. Clone your fork
git clone https://github.com/ramtinkosari/Team.git
cd Team

# 3. Add the canonical repo as upstream
git remote add upstream https://github.com/QSSLibrary/Team.git

# (per work item)
# 4. Sync main
git checkout main
git fetch upstream
git merge upstream/main
git push origin main

# 5. Create a branch with a convention-compliant name
git checkout -b wg/celestial-mechanics

# 6. Make changes (e.g., create a proposal file)
mkdir -p proposals
# ...write the proposal content using templates/proposal.md as a guide...

# 7. Commit with DCO sign-off
git add proposals/wg-celestial-mechanics.md
git commit -s -m "Propose Celestial Mechanics WG

Adds a proposal for a new working group covering
celestial mechanics primitives, orbital dynamics,
and ephemeris handling.

Signed-off-by: Ramtin Kosari <ramtinkosari@example.com>"

# 8. Push to your fork
git push origin wg/celestial-mechanics

# 9. Open the PR in your browser:
# https://github.com/QSSLibrary/Team/compare/main...ramtinkosari:wg/celestial-mechanics?template=wg-proposal.md

# 10. Fill in the PR body, request review, address feedback

# 11. Once merged, sync your fork and delete the branch
git checkout main
git fetch upstream
git merge upstream/main
git push origin main
git branch -d wg/celestial-mechanics
git push origin --delete wg/celestial-mechanics
```

## 13. Cross-references

- `BRANCH-NAMING.md` — branch naming convention
- `CONTRIBUTING.md` — overall contribution workflow
  and policies
- `CODE_OF_CONDUCT.md` — community standards
- `policies/licensing-and-cla.md` — DCO and
  corporate-contributions policy
- `templates/proposal.md` — proposal content
  template
- `templates/joint-proposal.md` — joint proposal
  content template
- `.github/PULL_REQUEST_TEMPLATE/` — PR body
  templates
- `governance/working-groups.md` §6.2 — joint
  decision process (relevant to joint proposals)
- `governance/evolution.md` §6.2 — how governance
  is amended
- `standards/git-workflow.md` (Phase 2) — commit
  conventions, merge strategy, etc.

## 14. Decision log

| Version | Date | Summary | Authority |
|---|---|---|---|
| 1.0 | 2026-08-08 | Initial PR workflow document for outside collaborators. Covers the fork-and-PR model, the GitHub URL parameter procedure, the full PR creation flow, what outside collaborators can and cannot do, common pitfalls, and a worked example. | Project lead |

---

*This document is the canonical reference for
outside-collaborator PR workflow in the `Team`
repository. It is expected to be amended as the
project's tooling and conventions evolve. The most
reliable statement of the workflow is always the
latest version of this file in the repository.*
