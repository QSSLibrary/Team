# QSSL Contributing Guide

> The entry point for contributing to the QSSL project.
> This document is the **map** — it orients new contributors
> and points to the **territory** (the detailed docs) for each
> topic it touches. If you are new to QSSL, start here.
>
> **Status:** Active
> **Version:** 1.0
> **Effective date:** 2026-08-08
> **Supersedes:** none
> **Amends:** none
> **Authoritative copy:** this file at the root of the
> `QSSLibrary/Team` repository

---

## 1. Welcome

QSSL is built by its contributors — researchers, students,
educators, game and simulation developers, aerospace engineers,
amateur astronomers, and curious people who care about
computational astronomy being correct, well-tested, and freely
available. First-time contributors and experienced maintainers
are equally welcome.

Three things to know about QSSL's culture up front:

- **Open by default.** Discussions, proposals, and decisions
  happen in public channels (GitHub Issues, GitHub Discussions,
  Discord, public PRs). Private DMs are for coordination, not
  governance. Per `GOVERNANCE.md` §8, **decisions are not made
  in DMs.**
- **Stewardship, not ownership.** No company, individual, or
  institution owns QSSL. The project exists independently of its
  founders and contributors. See `CHARTER.md` §4 and §5.
- **Scientific correctness is non-negotiable; engineering
  choices are negotiable.** When the domain side (QSS Corp.) and
  the engineering side (Cuby Inc.) disagree, scientific correctness
  wins; engineering accommodates it. See `CHARTER.md` §5.1 and
  `GOVERNANCE.md` §4.3.

If you read nothing else in this document, read **§2 (Code of
Conduct)** and **§6 (Pull requests)**.

---

## 2. Code of Conduct

Every QSSL community space is governed by our Code of Conduct,
which adopts the **Contributor Covenant 2.1** verbatim. Read it
before your first contribution:

- `CODE_OF_CONDUCT.md` — the full Code, plus QSSL-specific
  application notes for community spaces, reporting, and appeals.

The short version: be respectful, be constructive, give and accept
feedback gracefully, focus on what's best for the community. The
full version, the enforcement guidelines, and how to report a
violation are in `CODE_OF_CONDUCT.md`.

---

## 3. Where things happen

Different kinds of work go in different places. Using the right
venue gets your contribution seen faster and reviewed by the right
people.

| You want to... | Use this venue | See |
|---|---|---|
| Report a bug | GitHub Issue on the affected repository | §4.1 |
| Request a feature | GitHub Issue on the affected repository | §4.2 |
| Report a scientific error (wrong formula, off-by-one, etc.) | GitHub Issue, labeled `scientific-correction` | §4.3 |
| Propose a change to existing code or docs | Pull Request | §5.2, §6 |
| Propose a new working group | Proposal PR to `proposals/` | §5.3 |
| Propose a governance change | Proposal PR to `proposals/` or directly to a `gov/` branch | §5.3 |
| Discuss an idea before formalizing it | GitHub Discussions on the relevant repository, or Discord | §5.1 |
| Report a security vulnerability | Private channel per `SECURITY.md` (forthcoming) | — |
| Report a Code of Conduct violation | Per `CODE_OF_CONDUCT.md` §3.3 | — |

When in doubt, **start in GitHub Discussions or Discord**. The
community will help you route your idea to the right venue.

---

## 4. Filing issues

A useful issue is a small piece of writing. The more context you
give, the faster the right person can act on it.

### 4.1 Bug reports

A useful QSSL bug report includes:

- **What you were doing.** The command you ran, the code you
  wrote, the workflow you were following. Include the actual
  command line, the relevant code snippet, or both.
- **What you expected.** The correct or desired outcome.
- **What actually happened.** The actual outcome, including any
  error messages, warnings, or unexpected output. Copy-paste the
  error verbatim where possible.
- **Environment.** QSSL version (or commit hash if built from
  source), compiler and version (`g++ --version`,
  `clang++ --version`, or `cl.exe`), operating system, build
  flags, and any relevant CMake or system configuration.
- **Minimal reproducer.** The smallest code snippet, build
  invocation, or test case that demonstrates the bug. Smaller is
  better.

Issue templates (bug report, feature request) are added **per
repository**, in each repository's `.github/ISSUE_TEMPLATE/`. Until
a template is added to the relevant repository, a clear title and
the structure above are sufficient.

### 4.2 Feature requests

A useful feature request includes:

- **The problem you want to solve**, not just the solution. "I
  need to convert ICRS coordinates to galactic at high precision"
  is better than "please add an `icrs_to_galactic` function."
- **The proposed solution**, if you have one. It is fine to file
  a request without a proposed solution — describe the problem and
  the maintainers will help scope a solution.
- **Alternatives you considered**, including the option of doing
  nothing. This often saves time by surfacing constraints the
  requester didn't see.
- **Use cases.** Who else might benefit? Are there published
  references, prior art, or related libraries that address the
  problem?

### 4.3 Scientific corrections

QSSL is a scientific library. Some bugs are not just bugs —
they're wrong physics, wrong formulas, or wrong references. These
are filed as GitHub Issues with the **scientific-correction**
label, and they are treated with the highest priority.

A scientific correction report includes, in addition to the bug
report structure above:

- **The reference.** The published source (paper, IAU resolution,
  SOFA/ERFA documentation, textbook) that establishes the correct
  behavior. Citations are mandatory; an uncited "this looks wrong"
  is not actionable.
- **The expected value(s).** The numerical or symbolic result
  that the code should produce, ideally with a worked example or
  test case.
- **The actual value(s).** What the code currently produces.

Scientific corrections are reviewed by the relevant working group
lead or by the domain authority (QSS Corp. representative, per
`CHARTER.md` §5.1). Fixes are merged with priority and credited in
the release notes.

### 4.4 What happens after you file an issue

1. **Triage.** A maintainer or working group lead labels the
   issue, assigns it to the right area, and may ask for more
   context.
2. **Discussion.** Anyone can comment. Substantive disagreements
   are handled per `GOVERNANCE.md` §5.
3. **Resolution.** Either a PR fixes the issue, the issue is
   closed (with reason), or it is converted into a proposal for
   larger changes.

Issues are not abandoned silently. If an issue stalls, ask in
Discord or in the relevant working group's channel.

---

## 5. Proposing changes

QSSL distinguishes between three tiers of change. The right venue
depends on which tier your change falls into.

### 5.1 Tier 1: discussion first

Use **GitHub Discussions** or **Discord** when:

- You're not sure what the right approach is
- You want feedback on an idea before writing code
- The change involves a design or scope question that the
  community should weigh in on
- You're new to QSSL and want to orient yourself

A discussion thread often becomes a proposal (§5.3) or a PR
(§5.2). The output of a discussion is a decision: do we want to
do this? If yes, in what form?

### 5.2 Tier 2: a pull request

Use a **pull request** when:

- The change is well-scoped (one feature, one fix, one doc
  update)
- The approach is clear or has been agreed in a prior discussion
- The change fits within an existing working group's scope (or
  no WG scope is affected)

This is the most common path. The PR review process is described
in §6 and §7.

### 5.3 Tier 3: a formal proposal

Use a **proposal PR to `proposals/`** when the change:

- Creates a new working group
- Adds or removes a public module
- Makes a breaking API change
- Changes project governance
- Establishes a new standard or policy
- Otherwise has a project-wide impact that warrants a public
  comment period

Proposals follow the standard proposal process (`GOVERNANCE.md`
§4.1):

1. **Proposal PR** opened using `templates/proposal.md` (or
   `templates/joint-proposal.md` for cross-WG work)
2. **Public comment period** of 7–14 days, depending on impact
3. **Decision** by the project lead (Phase 1) or TSC (Phase 2+),
   with reasons documented
4. **Recording** as an ADR in `decisions/` if accepted
5. **Implementation** in subsequent PRs to the relevant
   repository

Proposals that are rejected can be revised and resubmitted. There
is no appeal from a rejection, but a fresh proposal is always
welcome.

---

## 6. Pull requests

The detailed fork-and-PR walkthrough is in **`PR-WORKFLOW.md`**.
This section is the quick orientation.

### 6.1 The 60-second version

1. **Fork** the relevant `QSSLibrary/<repo>` to your account
2. **Branch** with a convention-compliant name (per
   `BRANCH-NAMING.md`)
3. **Commit** with `git commit -s` to add the DCO
   `Signed-off-by:` line (per `policies/licensing-and-cla.md`)
4. **Push** to your fork
5. **Open a PR** using a compare URL with the appropriate
   template (`.github/PULL_REQUEST_TEMPLATE/`)

For the full walkthrough — URL syntax, syncing your fork, common
pitfalls, and a worked example — see `PR-WORKFLOW.md`.

### 6.2 Branch naming

Branch names in the `Team` repository follow `BRANCH-NAMING.md`.
Briefly:

| Prefix | Use for |
|---|---|
| `wg/<name>` | Working group proposal or WG-related change |
| `gov/<name>` | Governance document change |
| `std/<name>` | Standard, policy, or guideline change |
| `decisions/<name>` | Architecture Decision Record (ADR) |
| `joint/<name>` | Joint WG proposal (cross-WG) |
| `topic/<name>` | Anything else (typos, small docs, etc.) |

For library repositories (e.g., `QSSLibrary/qssl`), a separate
branch-naming convention will be defined in
`standards/git-workflow.md` (Phase 2).

### 6.3 DCO sign-off

Every commit in QSSL must have a `Signed-off-by:` line. This is
the **Developer Certificate of Origin (DCO)** — a lightweight
attestation that you wrote the contribution or have the right to
submit it. The full policy, including the corporate-authorization
clause, is in `policies/licensing-and-cla.md`.

To add the sign-off line to your commits:

```bash
git commit -s -m "Your commit message"
```

To retroactively sign off a previous commit:

```bash
git commit --amend --signoff --no-edit
```

For multiple commits, use `git rebase` with `git commit --amend
--signoff --no-edit` per commit, then force-push.

### 6.4 Commit messages

#### 6.4.1 Rules for contributors

A good commit message:

- Has a short summary line (≤72 characters) that completes the
  sentence "This commit will..."
- Uses the **imperative mood** ("Add", "Update", "Remove",
  "Fix", "Refactor" — not "Added", "Adds", "Adding"). Pick the
  first word that fits; all five forms above are acceptable
  imperatives.
- Has a blank line after the summary, then a longer body if
  needed (wrap at ~72 characters)
- References relevant issues and PRs with GitHub-native
  linking, which auto-links on github.com:
  - `(refs #123)` — general reference
  - `(#123)` — short form
  - `Fixes #123` / `Closes #123` — when the commit definitively
    closes the issue or PR
- Includes the `Signed-off-by:` line (added by `-s`)

**Squash-merge behavior.** The project lead normally squashes
contributor commits on merge. The final commit message is
rewritten by the maintainer to apply the project's
`[#<type>]` tag convention (see §6.4.2). Contributors do not
need to use the `[#<type>]` prefix themselves — that is a
maintainer step, applied on merge.

#### 6.4.2 Project-lead commit convention (informational)

This subsection documents the commit-message style used by the
project lead in QSSL repositories. **Contributors are not
required to follow it for their own commits** — the squash-merge
step in §6.4.1 takes care of applying the tag in the final
history. **Contributors who choose to follow it are welcome to
do so.** If your commits already carry the `[#<type>]` tag and
the message follows this convention, the maintainer will
preserve your message on merge instead of rewriting it.

**Format:**

```
[#<type>](?#<id>) <imperative message>
```

- `type` — a content-area tag indicating what kind of file the
  commit touches. This is independent of the branch prefix
  (which describes the kind of change).
- `id` (optional) — an issue or PR number; renders as a
  clickable GitHub link.

**Examples from current history:**

- `[#GOVERNANCE] Add Working Groups Document`
- `[#CONDUCT] Add Code of Conduct Document`
- `[#PR](#21) Update Proposals PR Templates`

**Approved types in the `Team` repository:**

| Tag | Used for |
|---|---|
| `[#CHARTER]` | Changes to `CHARTER.md` |
| `[#GOVERNANCE]` | Changes to `GOVERNANCE.md` and files in `governance/` |
| `[#TEMPLATE]` | Changes to `templates/` or `.github/PULL_REQUEST_TEMPLATE/` |
| `[#BRANCH]` | Changes to `BRANCH-NAMING.md` |
| `[#PR]` | Changes to `PR-WORKFLOW.md` |
| `[#CONDUCT]` | Changes to `CODE_OF_CONDUCT.md` |
| `[#CONTRIBUTING]` | Changes to `CONTRIBUTING.md` |
| `[#POLICY]` | Changes to `policies/*` |
| `[#SECURITY]` | Changes to `SECURITY.md` |
| `[#README]` | Changes to `README.md` |
| `[#LICENSE]` | Changes to `LICENSE` / `NOTICE` |
| `[#PROPOSAL]` | Changes to `proposals/`, `decisions/`, or working-group structure |
| `[#TOPIC]` | Catch-all for anything not covered above (typo fixes, small docs, etc.) |

**Extension to library repositories.** When the QSSL library
repository exists, the convention extends with module-level
tags such as `[#SUBMODULE]`, `[#TEST]`, `[#DOCS]`,
`[#EXAMPLE]`, scoped to the library's module structure (e.g.,
`[#SUBMODULE] Update Spherical Astronomy`). The vocabulary
for library code will be formalized when the library repo is
created.

**Phase 2 follow-up.** When the `standards/` directory is
established (per `ARCHITECTURE.md` line 278 — Phase 2, "when
2+ external contributors exist and PRs start flowing"), this
convention may be moved to `standards/commit-style.md` and
referenced from this subsection. Until then, it lives here in
`CONTRIBUTING.md`.

### 6.5 PR size

Per `PR-WORKFLOW.md` §11.5, the convention is:

- **Small PRs preferred.** Aim for **<300 lines** of changes per
  PR.
- **Split large changes** into multiple PRs by feature, file, or
  concern.
- **Use draft PRs** for work-in-progress that isn't ready for
  review (`?draft=true` in the compare URL, or the "Create draft
  pull request" option).

A PR that's too large to review in one sitting is a PR that won't
get reviewed in one sitting.

---

## 7. The review process

### 7.1 Timing

Per `GOVERNANCE.md` §6.2, the project's target is:

| Milestone | Target |
|---|---|
| First response | Within **7 days** of opening the PR |
| Merge or close | Within **30 days**, unless there's a good reason for delay |

A "good reason for delay" includes:

- The change requires a proposal first (per §5.3)
- The change is blocked on a scientific question for a domain
  expert
- The change is blocked on external review (e.g., a security
  review, a legal question)
- The relevant maintainer is unavailable, with notice

If your PR has not received a response within 7 days:

1. **Ping the reviewer** with a comment on the PR
2. **If still no response** after another 7 days, mention the
   project lead or the relevant working group lead
3. **If still no response** after a total of 21 days, escalate
   per `GOVERNANCE.md` §5.3

Maintainer unavailability is normal. Most "stuck" PRs are stuck
for a substantive reason that the reviewer will explain.

### 7.2 What reviewers look for

Reviewers in QSSL check for:

- **Scientific correctness** (domain authority per `CHARTER.md`
  §5.1) — does the code match the published convention, formula,
  or reference? Are units, reference frames, and time scales
  handled correctly?
- **Engineering quality** (technical authority per `CHARTER.md`
  §5.1) — is the code well-tested, idiomatic for the chosen C++
  version (`CHARTER.md` §6), performant, and documented?
- **API design** — does the change fit the project's existing
  API style? When the API style is published (`standards/api-design.md`,
  Phase 2), the change is checked against it.
- **DCO sign-off** — every commit must have a `Signed-off-by:`
  line per `policies/licensing-and-cla.md`
- **Branch naming** — per `BRANCH-NAMING.md`
- **CoC compliance** — the discussion in the PR is conducted per
  `CODE_OF_CONDUCT.md`

Reviewers may request changes, approve, or close the PR with a
reason. Close-with-reason is not a rejection of the contributor;
it is a routing decision (e.g., "this needs to be a proposal
first" or "this is out of scope per `CHARTER.md` §3.2").

### 7.3 Iterative review

Reviews are iterative. Push new commits to your branch — the PR
updates automatically. You don't need to close and reopen.

When addressing feedback:

- **Prefer separate commits.** This lets the reviewer see the
  diff against their comments clearly. The merge step can squash
  if appropriate.
- **Reply to comments** with a brief note explaining what you
  did, even if the change is small ("Fixed in 3f5a8b2").
- **Resolve threads** when addressed. The reviewer may re-open a
  thread if they want to recheck.

### 7.4 If your PR is closed

A closed PR is not a ban. A PR may be closed for:

- **Superseded** by another PR
- **Out of scope** (per `CHARTER.md` §3.2)
- **Needs a proposal first** (per §5.3)
- **Stale** (no response from the contributor for 60+ days after
  a review request)
- **Duplicate** of an existing PR or issue

If your PR was closed for a reason you don't agree with, the
dispute-resolution procedures in `GOVERNANCE.md` §5 apply. You can
also open a new PR or proposal that addresses the closure
reason.

---

## 8. Working groups

Working groups (WGs) are the project's coordination structure for
focused scientific or technical areas. A detailed description of
how WGs work is in `governance/working-groups.md`. This section is
the contributor-facing summary.

### 8.1 How to find the right WG

Working groups are listed in `governance/working-groups.md`. Each
WG has:

- A **Discord channel** (e.g., `#wg-cosmology`)
- A **GitHub team** with `@wg-cosmology` mention capability
- A **GitHub Discussions area** for WG-internal matters
- A **scope** (the area the WG owns; see §8.3)

To find the right place for your contribution:

1. Identify the topic (e.g., "celestial mechanics", "imaging",
   "build system")
2. Look up the WG that owns that scope, or note that no WG owns
   it yet
3. Engage in the WG's Discord channel or GitHub Discussions area

### 8.2 Joining a WG

Joining is by self-selection. Express interest in the WG's Discord
channel, GitHub team, or relevant issue/PR. The WG lead may
accept or decline based on capacity. There is no formal
application process.

You can be a member of **multiple WGs** simultaneously, or of
**no WG at all**. **WG membership is not a gate to contribution.**
Any contributor can submit PRs to any QSSL repository, regardless
of WG membership. The WG structure is for **coordination**, not
**access control** — see `governance/working-groups.md` §9.3.

### 8.3 Scope discipline

A WG's scope is the area it owns. PRs and issues within that
scope are routed to the WG for triage and review. Cross-scope work
follows the joint decision process (`governance/working-groups.md`
§6.2).

If you want to do work that doesn't clearly fit any WG's scope,
open a GitHub Discussion first. The community will help route it.

---

## 9. Decision-making

Decisions in QSSL are made publicly and recorded. The full process
is in `GOVERNANCE.md` §4. This section is the contributor-facing
summary.

### 9.1 Day-to-day decisions

Most decisions — what to fix, what to build next, how to refactor
existing code — are made in GitHub Issues, GitHub Discussions, and
PRs. Anyone can participate. The relevant maintainer or working
group lead makes the call.

### 9.2 Governance, scope, and API decisions

Decisions that affect project-wide concerns — governance, scope,
new modules, breaking API changes, new standards — go through the
formal proposal process (§5.3). The proposal is discussed publicly
for 7–14 days and decided by the project lead (Phase 1) or TSC
(Phase 2+).

### 9.3 Recording

Decisions are recorded where they happen:

- **Technical decisions** — recorded in the PR description and
  commit messages of the merging PR
- **Governance and scope decisions** — recorded as ADRs in
  `Team/decisions/` (per `GOVERNANCE.md` §4.1)
- **Charter-level decisions** — recorded in the decision log at
  the bottom of `CHARTER.md` §8.3

There are no closed-door decisions in governance or scope matters.
If you find a decision that was made off-record, raise it on a
GitHub Issue — it will be re-discussed and recorded.

---

## 10. Recognition

QSSL is built by its contributors, and the project records
contribution **open by default**. There are no private "thank
you" channels; recognition happens in public artifacts.

### 10.1 Where contributions are recorded

- **GitHub contributors graph** of each repository —
  automatically maintained by GitHub. The authoritative list of
  who has contributed what.
- **`AUTHORS` file** — to be added per repository in Phase 2;
  will list significant contributors (sustained activity,
  substantial PRs, or other notable contributions).
- **Working-group ADRs** — WG-founding ADRs list initial members;
  WG-internal ADRs credit significant contributions.
- **Release notes** — significant contributions are credited in
  release notes.
- **Decision records** — `decisions/` ADRs credit the contributors
  who proposed, reviewed, and finalized each decision.

### 10.2 Maintainer status

Contributors who demonstrate sustained, high-quality contributions
and judgment are eligible for maintainer status. There is no fixed
formula; the project lead (Phase 1) or TSC (Phase 2+) makes the
call. Indicators are listed in `GOVERNANCE.md` §6.1. Maintainer
status is **not** a reward for contribution count alone — it is
an entrustment of judgment.

### 10.3 The contributors list

The current list of significant contributors is visible in:

- The GitHub contributors graph of each repository
- The contributors list of each WG (in the WG's founding ADR,
  when one exists)

QSSL does not maintain a single global contributors list — it
maintains one per repository and one per working group. This is
intentional: it makes credit local to the place the work happened.

---

## 11. If you need help

### 11.1 Channels for questions

| Question type | Channel |
|---|---|
| Bug report or feature request | GitHub Issue on the relevant repository |
| Design or scope question | GitHub Discussions on the relevant repository, or Discord (`#general`) |
| Working-group question | The relevant WG's Discord channel |
| Quick chat or community question | Discord (`#general`, `#introductions`, or the relevant WG) |
| Code of Conduct concern | See `CODE_OF_CONDUCT.md` §3.3 |
| Security vulnerability | See `SECURITY.md` (forthcoming) |
| Anything else | Discord `#general`, or open a GitHub Discussion |

### 11.2 Don't DM maintainers

Per `GOVERNANCE.md` §8, **decisions are not made in DMs.** If you
have a question that requires a decision — about scope, design,
acceptance of a contribution, or anything else — post it
publicly. Maintainers may direct you to the right venue, but they
will not adjudicate substantive questions in private.

DMs are fine for coordination ("Are you free for a quick call
about issue #123?"). They are not fine for governance.

### 11.3 Patience and persistence

Open-source maintainers are volunteers or part-time contributors.
Response times vary. If you don't get an answer in a week, ping
politely. If you don't get an answer in two weeks, the
escalation path in §7.1 applies. Patience and persistence beat
frustration, every time.

---

## 12. Cross-references

- `README.md` — entry point for the `Team` repository
- `CODE_OF_CONDUCT.md` — community standards and enforcement
- `CHARTER.md` — what QSSL is, mission, scope, governance
  philosophy, founding stewardship
- `GOVERNANCE.md` — how QSSL is run, decision-making, maintainer
  lifecycle, conflict resolution
- `BRANCH-NAMING.md` — branch naming convention
- `PR-WORKFLOW.md` — outside-collaborator PR workflow (fork,
  clone, push, compare URL, worked example)
- `policies/licensing-and-cla.md` — DCO sign-off policy and
  corporate-authorization clause
- `governance/working-groups.md` — working group rules
- `governance/roles.md` — role definitions
- `governance/sponsorship.md` — Cuby Inc. ↔ QSS Corp. founding
  agreement
- `governance/evolution.md` — phase transition procedures
- `templates/proposal.md` — proposal content template
- `templates/joint-proposal.md` — joint proposal content
  template
- `.github/PULL_REQUEST_TEMPLATE/` — PR body templates
- `SECURITY.md` (forthcoming) — vulnerability disclosure policy

---

## 13. Decision log

| Version | Date | Summary | Authority |
|---|---|---|---|
| 1.0 | 2026-08-08 | Initial contributing guide. Covers welcome and culture (§1), Code of Conduct pointer (§2), venues (§3), filing issues (§4 — bug reports, feature requests, scientific corrections), proposing changes (§5 — three-tier model: discussion, PR, proposal), pull request quick-orientation (§6), the review process including timing SLOs and what reviewers look for (§7), working groups as a contributor-facing coordination structure (§8), decision-making summary (§9), open-by-default recognition (§10), and help channels with the "don't DM maintainers" rule (§11). To be expanded with `SECURITY.md` and `AUTHORS`-file references once those policies and per-repo files exist. | Project lead |

---

*This document is the canonical contributor entry point for
QSSL. It is expected to be amended as the project's processes
evolve. The most reliable statement of how to contribute to
QSSL is always the latest version of this file in the
repository.*
