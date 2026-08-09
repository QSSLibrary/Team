# Joint Proposal Template
> [!Important]
> ## How to use this template as a GitHub PR
>
> This file is a **content template** — a complete
> document skeleton for a joint WG proposal. It is
> **not** the PR template that GitHub pre-fills into
> the PR body.
>
> The PR templates that GitHub pre-fills live in
> `.github/PULL_REQUEST_TEMPLATE/` of this repository.
> The detailed content for the actual joint proposal
> goes in this file (or in a markdown file in
> `proposals/`). Both layers exist intentionally: the
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
> Example for a joint proposal on a branch
> `joint/spherical-astronomy`:
>
> ```
> https://github.com/QSSLibrary/Team/compare/joint/spherical-astronomy?template=joint-proposal.md
> ```
>
> GitHub looks up `<template-name>.md` in
> `.github/PULL_REQUEST_TEMPLATE/` and pre-fills the
> PR body with its contents.
>
> ### Branch naming convention
>
> Use the **`joint/<short-name>`** branch prefix for
> joint proposals. The full convention is in
> `BRANCH-NAMING.md` at the root of this repository.
>
> ---
>
> A template for **joint proposals** — formal
> proposals for cross-WG work that requires
> collaboration between multiple working groups.
>
> Used when a piece of work falls in two or more WGs'
> scopes and the WGs decide to handle it via the
> joint decision process per
> `governance/working-groups.md` §6.2. The joint
> proposal is the artifact produced by the joint
> working session and reviewed by all affected WGs.

---

## Joint Proposal: [Short, descriptive title]

**Date:** [YYYY-MM-DD]

**Author(s):** [your name and GitHub handle, plus
any co-authors]

**Affected WGs:** [list of WG names]

**Affected WG leads:** [list of leads, one per
affected WG]

**Joint session date:** [date of the joint
working session that produced this proposal]

---

## 1. Summary

One-paragraph summary of the cross-WG work. State
the change in plain language.

## 2. Origin

How did this joint work come about? Was it proposed
by a WG, by a user, by the project lead, by an RG?
Cite the originating issue, discussion, or
conversation.

## 3. Joint Session Notes

Summary of the joint working session that produced
this proposal:

- **Attendees:** [names and roles]
- **WGs represented:** [list]
- **Key decisions made:** [bulleted]
- **Open questions resolved:** [bulleted]
- **Open questions remaining:** [bulleted, if any]

If there was no formal session (e.g., a
small change coordinated in chat), summarize the
asynchronous coordination here.

## 4. Shared Scope

What is the cross-WG work, precisely? Define the
boundary of the work — what is in scope, what is
not.

## 5. Contributions of Each WG

For each affected WG, list its specific
contribution to the work:

- **WG: [name]**
  - **Lead:** [name]
  - **Contributes:** [what this WG is responsible
    for]
  - **Owns in the final code:** [files, modules,
    or areas the WG will own]
  - **Reviews:** [what this WG reviews from other
    WGs' contributions]

Repeat for each affected WG.

## 6. Approach

The agreed technical and/or scientific approach.
Be specific:

- Algorithms chosen (with citations if relevant)
- Conventions followed (IAU, SOFA, etc.)
- API design
- Test strategy
- Documentation approach

## 7. Implementation Plan

How the work will be split, sequenced, and
delivered:

- **Phase 1:** [what, who, by when]
- **Phase 2:** [what, who, by when]
- **Dependencies between WGs:** [which WG's work
  blocks which]
- **PR ordering:** [which PRs need to merge in
  which order]
- **Cross-WG review:** [how will reviewers from
  different WGs coordinate]

## 8. Cross-WG Review Coordination

How will cross-WG code review work? Specifically:

- Who reviews which parts?
- What happens if a reviewer from one WG has
  concerns about another WG's work?
- How are review conflicts resolved?
- Is there a designated cross-WG reviewer for
  the integration PR?

## 9. Success Criteria

How will we know the joint work succeeded? What
metrics or signals indicate success or failure?

## 10. Risks and Mitigations

What could go wrong? How will risks be mitigated?

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| [risk 1] | [L/M/H] | [L/M/H] | [mitigation] |
| [risk 2] | ... | ... | ... |

## 11. References

Links to:
- Originating issue or discussion
- Related issues, PRs, and proposals
- Scientific literature (if applicable)
- Existing WG documentation
- ADRs that informed the approach

---

## Per-WG Review and Approval

Per `governance/working-groups.md` §6.2, a joint
proposal is accepted when every affected WG accepts
it (no objections in any WG's lazy-consensus window,
per §8.2 — default 3 days). The proposal author
coordinates the per-WG review process.

For each affected WG, document its review:

### WG: [name]

- **Lead:** [name]
- **Consensus window:** [start] to [end] (≥3 days)
- **Result:** [accepted / accepted with
  conditions / objected]
- **Notes:** [any specific concerns, conditions,
  or amendments from this WG's review]

### WG: [name]

[repeat for each affected WG]

### Final outcome

- **All WGs accepted?** [yes / no]
- **Conditions to address:** [bulleted, if any]
- **Joint proposal status:** [accepted /
  accepted with conditions / withdrawn / escalated
  to project lead or TSC]

If any WG objected, the joint decision process per
`governance/working-groups.md` §6.2 applies. The
escalation path is to the project lead (Phase 1) or
TSC (Phase 2+).

---

## Reviewer Notes

(This section is for the review process, not the
author.)

### Discussion

[Summary of the public discussion, including
objections raised and addressed]

### Final Decision

[Decision with date, and which WGs accepted /
objected]

### Implementation Tracking

[Links to implementation PRs and ADRs]

---

*After acceptance, this joint proposal becomes a
working agreement between the affected WGs. It is
referenced in implementation PRs and recorded in
`decisions/` as an ADR if the decision is
charter-level or governance-level.*
