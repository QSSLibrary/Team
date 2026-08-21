# QSSL Team Repository — Branch Naming Convention

> The canonical, committed reference for the branch
> naming convention used in the `QSSLibrary/Team`
> repository. This document is **committed** (not a
> working note) and is intended to be visible to all
> contributors, including outside collaborators.
>
> For the broader repository architecture, see
> `README.md` and `ARCHITECTURE.md` (the latter is
> working notes). For the development workflow
> overview, see `CONTRIBUTING.md`.

---

## 1. Why we have a convention

The `Team` repository hosts proposals, governance
documents, working-group rules, standards, policies,
and other governance artifacts. As the project grows,
the number of open branches will grow too. A
consistent naming convention:

- Makes branches easy to find and group
- Prevents accidental branch reuse
- Supports the `?template=` URL parameter for
  GitHub PR templates
- Allows the project lead or TSC to clean up
  stale branches systematically
- Lets new contributors navigate the repository
  without confusion

The convention is **enforced by the project lead and
TSC during PR review** — a PR from a branch with a
non-conforming name is asked to rename. It is **not**
automatically rejected; the bar is low.

## 2. The convention

Use these branch-name prefixes:

| Prefix | Used for | Example |
|---|---|---|
| `wg/<name>` | New working-group proposal | `wg/celestial-mechanics` |
| `gov/<name>` | Governance document change | `gov/charter-amendment-v2` |
| `std/<name>` | Standard, policy, or guideline change | `std/cpp-style-update` |
| `decisions/<name>` | Architecture Decision Record (ADR) | `decisions/adr-001-cpp20` |
| `joint/<name>` | Joint WG proposal (cross-WG collaboration) | `joint/spherical-astronomy` |
| `topic/<name>` | Anything else (typo fixes, small docs, etc.) | `topic/fix-typo` |

### 2.1 Rules

1. **Lowercase.** All branch names are lowercase.
2. **Hyphens, not underscores or spaces.** Use
   hyphens between words: `wg/celestial-mechanics`,
   not `wg/celestial_mechanics` or
   `wg/celestial mechanics`.
3. **Short names.** Aim for 2–4 words after the
   prefix. Avoid long descriptive names; the PR
   description and linked issues carry the detail.
4. **One branch per change set.** Do not reuse
   branches across unrelated changes. Each proposal
   or change set gets its own branch.
5. **Delete merged branches.** When a PR is merged,
   delete the source branch. GitHub offers this
   automatically on PR merge; the project lead or
   TSC should configure the repository to
   auto-delete.
6. **No generic names.** Avoid `dev`, `test`,
   `temp`, `wip`, `new`, `my-changes`, etc. Use a
   specific prefix from the table above.
7. **Match the prefix to the change type.** If the
   change touches a governance document, use
   `gov/`. If it proposes a new standard, use
   `std/`. The prefix tells reviewers what kind of
   review to expect.

### 2.2 Examples

**Good:**

- `wg/celestial-mechanics` — new WG proposal
- `wg/cosmology` — new WG proposal (short and clear)
- `gov/charter-amendment-v2` — second attempt at
  amending the charter
- `std/cpp-style-update` — updating the C++ style
  standard
- `decisions/adr-001-cpp20` — ADR recording the
  C++20 floor decision
- `joint/spherical-astronomy` — joint proposal
  involving Celestial Sphere WG and Spherical
  Trigonometry WG
- `topic/fix-typo-in-charter` — fixing a typo

**Bad:**

- `dev` — too generic
- `WIP` — too generic; doesn't describe the change
- `my-changes` — doesn't follow a recognized prefix
- `celestial_mechanics` — wrong case, missing
  prefix
- `wg/Celestial-Mechanics` — wrong case
- `wg/celestial-mechanics-wg-initial-proposal-final-v2`
  — too long
- `charter-update` — wrong prefix; use
  `gov/charter-update`

## 3. Integration with PR templates

The `?template=` URL parameter in GitHub's compare
URL can be combined with a properly named branch to
pre-fill the PR body with the right template.

The compare URL format is:

```
https://github.com/QSSLibrary/Team/compare/<branch>?template=<template-name>.md
```

GitHub looks up `<template-name>.md` in
`.github/PULL_REQUEST_TEMPLATE/` and pre-fills the
PR body with its contents.

### 3.1 Common combinations

| Branch prefix | PR template | Use case |
|---|---|---|
| `wg/<name>` | `wg-proposal.md` | New working-group proposal |
| `gov/<name>` | `governance.md` | Governance document change |
| `std/<name>` | `standards-policy.md` | Standard, policy, or guideline change |
| `decisions/<name>` | `governance.md` | ADR (uses governance template) |
| `joint/<name>` | `joint-proposal.md` | Joint WG proposal (cross-WG collaboration) |
| `topic/<name>` | (default) | Anything else |

### 3.2 Example URLs

- New WG proposal:
  ```
  https://github.com/QSSLibrary/Team/compare/wg/celestial-mechanics?template=wg-proposal.md
  ```
- Governance change:
  ```
  https://github.com/QSSLibrary/Team/compare/gov/charter-amendment-v2?template=governance.md
  ```
- Joint proposal:
  ```
  https://github.com/QSSLibrary/Team/compare/joint/spherical-astronomy?template=joint-proposal.md
  ```

## 4. Outside collaborators and forks

The branch naming convention applies equally to
outside contributors. The workflow is:

1. **Fork** `QSSLibrary/Team` to your own GitHub
   account. This creates `<your-username>/Team`.
2. **Create a branch** in your fork with a
   convention-compliant name (e.g.,
   `wg/celestial-mechanics`).
3. **Make changes** in that branch and **commit**
   with a DCO `Signed-off-by:` line.
4. **Push** the branch to your fork.
5. **Open a PR** from your fork's branch to
   `QSSLibrary/Team`'s base branch (typically
   `main`).

The compare URL for an outside contributor's fork
follows GitHub's standard cross-repo format:

```
https://github.com/QSSLibrary/Team/compare/main...<your-username>:<branch>?template=<template-name>.md
```

For example, if a contributor `alice` has a branch
`wg/cosmology` in their fork, the compare URL is:

```
https://github.com/QSSLibrary/Team/compare/main...alice:wg/cosmology?template=wg-proposal.md
```

This is the standard GitHub PR creation flow for
external contributors. Outside collaborators
**cannot push directly** to `QSSLibrary/Team`;
they must use a fork.

## 5. How the Team repository stays clean

To prevent branch proliferation:

- **Merged branches are deleted automatically.**
  GitHub offers this on PR merge. The project lead
  or TSC configures the repository to enable
  auto-delete of head branches after merge.
- **Stale branches are pruned.** Branches with no
  activity for 90+ days may be deleted by the
  project lead, with a courtesy notice to the
  branch author. Closed (but not merged) PRs are
  also candidates for branch deletion.
- **Branches are not re-used.** Each proposal or
  change set gets its own branch. This keeps the
  history clean and makes branch-level reviews
  possible.

## 6. Working groups and the convention

Working groups (per `governance/working-groups.md`)
typically do their work in their WG's own repository
or in QSSL's library repository, not in the `Team`
repository. The branch naming convention in this
document applies to the `Team` repository, which
hosts governance, proposals, and standards — not
library code.

For library code repositories, the branch naming
convention is documented in `standards/git-workflow.md`
(a Phase 2 document). The `Team` convention is
**independent** of the library convention, though
the prefixes share the same philosophy (semantic,
descriptive, lowercase, hyphens).

## 7. Cross-references

- `README.md` — Team repository entry point
- `CONTRIBUTING.md` — how to contribute (including
  PR creation flow)
- `templates/proposal.md` — proposal content
  template (uses the branch naming convention)
- `templates/joint-proposal.md` — joint proposal
  content template
- `.github/PULL_REQUEST_TEMPLATE/` — the PR
  templates pre-filled into the PR body
- `governance/working-groups.md` §6.2 — joint
  decision process (why the `joint/` prefix exists)
- `governance/evolution.md` §6 — governance
  amendment procedure (why the `gov/` prefix exists)
- `decisions/` — ADRs (why the `decisions/` prefix
  exists)
- `ARCHITECTURE.md` — working notes (not
  authoritative; cross-references this document)

## 8. Decision log

| Version | Date | Summary | Authority |
|---|---|---|---|
| 1.0 | 2026-08-08 | Initial branch-naming convention. Prefixes: `wg/`, `gov/`, `std/`, `decisions/`, `joint/`, `topic/`. Rules: lowercase, hyphens, short names, one branch per change set, no re-use. | Project lead |

---

*This document is the canonical reference for branch
naming in the `Team` repository. It is expected to
be amended as the convention evolves. The most
reliable statement of the convention is always the
latest version of this file in the repository.*
