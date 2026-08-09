# Proposal Template
> [!Important]
> ## How to use this template as a GitHub PR
>
> This file is a **content template** — a complete
> document skeleton for proposals, decisions, and
> other governance artifacts. It is **not** the PR
> template that GitHub pre-fills into the PR body.
>
> The PR templates that GitHub pre-fills live in
> `.github/PULL_REQUEST_TEMPLATE/` of this repository.
> The detailed content for the actual proposal goes
> in the body of the proposal file (e.g., a markdown
> file in `proposals/` or in the affected document's
> directory). Both layers exist intentionally: the
> PR template is for the **review process**, this
> content template is for the **artifact itself**.
>
> ### GitHub URL parameter procedure
>
> When you create a PR, you can ask GitHub to
> pre-fill the PR body with a specific template by
> using a `?template=` query parameter in the
> compare URL:
>
> ```
> https://github.com/QSSLibrary/Team/compare/<branch>?template=<template-name>.md
> ```
>
> Example for a new working-group proposal on a
> branch `wg/celestial-mechanics`:
>
> ```
> https://github.com/QSSLibrary/Team/compare/wg/celestial-mechanics?template=wg-proposal.md
> ```
>
> GitHub looks up `<template-name>.md` in
> `.github/PULL_REQUEST_TEMPLATE/` and pre-fills the
> PR body with its contents.
>
> ### Branch naming convention
>
> Use these branch-name prefixes to keep PRs
> organized and easy to find:
>
> | Prefix | Used for | Example |
> |---|---|---|
> | `wg/<name>` | New working-group proposal | `wg/celestial-mechanics` |
> | `gov/<name>` | Governance document change | `gov/charter-amendment-v2` |
> | `std/<name>` | Standard, policy, or guideline change | `std/cpp-style-update` |
> | `decisions/<name>` | ADR / decision record | `decisions/adr-001-cpp20` |
> | `joint/<name>` | Joint WG proposal (cross-WG collaboration) | `joint/spherical-astronomy` |
> | `topic/<name>` | Anything else | `topic/fix-typo` |
>
> Use lowercase, hyphens, and keep names short. One
> branch per proposal or change set; do not reuse
> branches across unrelated changes. This keeps the
> `Team` repository from accumulating many stale
> branches. The full branch naming convention is in
> `BRANCH-NAMING.md` at the root of this repository.
>
> ---

> A reusable template for any formal proposal to the
> QSSL project. Use this template for:
>
> - Proposing a new working group (§5.2 of
>   `governance/working-groups.md`)
> - Proposing a new policy, standard, or guideline
> - Proposing a charter or governance amendment
> - Proposing a phase transition
> - Proposing any other significant change
>
> Open this as a PR in `Team/proposals/`. Fill in
> every section. The proposal is reviewed and decided
> per the standard decision procedure described in
> `GOVERNANCE.md` §4.1.

---

## Proposal: [short, descriptive title]

**Author(s):** [your name and GitHub handle, plus any
co-authors]

**Date:** [YYYY-MM-DD]

**Status:** [Proposed / Under discussion / Accepted /
Rejected / Withdrawn]

**Decision authority:** [Project lead / TSC / Both
founders / etc., per the table in
`governance/evolution.md` §6.1]

---

## 1. Summary

One-paragraph summary of the proposal. State the
change in plain language.

## 2. Motivation

Why is this proposal needed? What problem does it
solve? What changes if we adopt it?

## 3. Detailed proposal

The full description of the proposed change. Be
specific. If the proposal modifies an existing
document, show the proposed changes (you can paste
diffs, or describe the changes section by section).

## 4. Alternatives considered

What other approaches were considered? Why was this
approach chosen? Be honest about trade-offs.

## 5. Drawbacks and risks

What are the downsides of this proposal? What could
go wrong? How can risks be mitigated?

## 6. Scope and applicability

What is affected by this proposal? Which
repositories, which working groups, which
contributors, which users?

## 7. Implementation plan

If the proposal is accepted, what are the next
steps? Who is responsible? What is the timeline?

## 8. Success criteria

How will we know if the proposal worked? What
metrics or signals will indicate success or
failure?

## 9. References

Links to related issues, discussions, prior
proposals, ADRs, and external references. For
scientific claims, include citations to peer-
reviewed literature.

## 10. Checklist (for working group proposals)

If this proposal is for a new working group, also
complete:

- [ ] **Name:** [WG name]
- [ ] **Type:** [leaf / parent / sub]
- [ ] **Scope:** [what the WG will and will not do]
- [ ] **Initial lead:** [name and GitHub handle]
- [ ] **Initial membership:** [list, or "to be recruited"]
- [ ] **Parent WG (if sub):** [parent WG name]
- [ ] **Rationale:** [why this WG should exist]
- [ ] **Overlap analysis:** [overlaps with existing WGs
      and how they will be managed]
- [ ] **GitHub Project entry created:** [link]

---

## Reviewer notes

(This section is filled in during the review
process, not by the author.)

### Discussion

[Summary of the public discussion, including
objections raised and addressed.]

### Decision

[Decision of the relevant authority, with date.]

### Implementation tracking

[Links to implementation PRs and ADRs.]
