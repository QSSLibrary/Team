# QSSL Governance

> The operational governance document of the QSSL project. Defines
> governance bodies, roles, decision-making processes, conflict
> resolution, and the maintainer lifecycle. The *charter* defines
> what QSSL is; this document defines how QSSL is run.
>
> **Status:** Active
> **Version:** 1.0
> **Effective date:** 2026-08-08
> **Supersedes:** none
> **Amends:** none
> **Authoritative copy:** this file at the root of the
> `QSSLibrary/Team` repository

---

## 1. Purpose and Scope

This document describes how QSSL is governed in practice. It covers:

- The bodies that hold decision authority at each phase of the
  project's life
- The roles within the project and what each is responsible for
- How decisions are proposed, discussed, made, and recorded
- How disagreements are resolved
- How maintainers are added, what they do, and how they leave
- How working groups are organized
- How the project transitions between governance phases

This document is operational. It does not define the project's
mission, scope, or identity — those are in `CHARTER.md`. It does
not define the founding stewards' relationship — that is in
`governance/sponsorship.md`. It does not define role details
beyond what is needed for the operational picture; detailed role
definitions are in `governance/roles.md`.

In the event of a conflict between this document and the charter,
the charter prevails.

## 2. Governance Bodies

QSSL's governance is structured to evolve. The current phase
defines which bodies exist and what authority they hold.

### 2.1 Phase 1 (current): founder-led

In Phase 1, the project is run by a small group of founding
stakeholders. The bodies are:

- **The project lead.** One of the two founders (currently
  designated by mutual agreement of the founders; see
  `governance/sponsorship.md`). The project lead holds
  primary day-to-day decision authority. Responsible for
  overall direction, release decisions, and final say on
  technical and governance questions not otherwise specified.
- **The founder representatives.** Both Cuby Inc. and QSS
  Corp. each designate one founder representative. The
  representatives are consulted on all significant decisions
  and hold veto authority on charter-level changes, on
  changes to this document, and on matters that fall within
  their respective domain or technical authority (see §3).
- **The QSS Corp. steering committee overseeing QSSL.** A
  group within QSS Corp. that oversees the project. Holds
  the discretion to determine when Phase 2 begins (see §9).
- **Maintainers (when appointed).** Contributors granted
  merge authority over specific areas of the project. See
  §6 and `governance/roles.md` for appointment and
  responsibilities.
- **Working groups (when established).** Self-organizing
  teams around focused scientific or technical areas.
  Working groups can be established in any phase, including
  Phase 1. In Phase 1, working group leads report to the
  project lead. See §7 and `governance/working-groups.md`
  for detailed rules.

There is no separate Technical Steering Committee (TSC) in
Phase 1. The functions a TSC would normally perform are
absorbed by the project lead, the founder representatives,
and the QSS Corp. steering committee, acting together.

### 2.2 Phase 2 (anticipated): TSC-led

When the QSS Corp. steering committee determines that the
library can be actively maintained under a TSC structure (see
CHARTER §5.3 and `governance/evolution.md`), the following
bodies are formed:

- **The Technical Steering Committee (TSC).** Comprises both
  founder representatives plus 1–3 external maintainers
  elected by the maintainer body. The TSC holds day-to-day
  decision authority. Decisions are made by simple majority
  unless this document specifies otherwise; the chair (elected
  by the TSC) breaks ties.
- **Maintainers.** Continue as in Phase 1, but with the TSC
  as the body that appoints and removes them.
- **Working groups.** Begin formal operation with leads
  reporting into the TSC.
- **Founder representatives.** Continue to sit on the TSC
  but transition to "stewardship" rather than "control" roles.
  Veto authority on charter-level changes is preserved.

### 2.3 Phase 3 (anticipated): foundation-hosted

When the TSC and founders jointly determine that the project
has reached a level of institutional adoption, sustained
funding need, or community demand that warrants legal and
financial independence (CHARTER §5.3), the project is
transferred to an independent fiscal host (e.g., NumFOCUS,
Open Source Collective, or a dedicated QSSL foundation):

- **Foundation board.** Hires, fires, and oversees the
  foundation. Independent of either founding company.
- **TSC (continuing).** Continues to make technical and
  operational decisions, but now reports to the board for
  matters of legal and financial consequence.
- **Maintainers, working groups, founder representatives.**
  Continue in their Phase 2 roles, with the addition that
  founder representatives transition from "stewardship" to
  "sponsorship" (i.e., they no longer hold formal authority
  unless elected to the TSC on their own merits).

## 3. Roles

This section summarizes roles. Detailed role definitions,
permissions, promotion and removal criteria, and conflict-of-
interest rules are in `governance/roles.md`.

### 3.1 Project lead (Phase 1 only)

**Current Phase 1 project lead: [Ramtin Kosari](github.com/ramtinkosari)**. This designation is by mutual agreement of
both founding stewards and is recorded in
`governance/sponsorship.md`.

The project lead holds:

- Primary day-to-day decision authority
- Final say on routine operations
- Responsibility for calling meetings, setting agendas, and
  preparing releases
- Subject to founder-representative consultation on
  significant matters
- Subject to founder veto on charter-level matters

The project lead is **not** a permanent position and **not**
a personal fiefdom. The role can be reassigned by founder
agreement (§3.4 of `governance/sponsorship.md`).

### 3.2 Founder representatives

- One each from Cuby Inc. and QSS Corp.
- Hold veto authority on charter-level and governance-level
  changes
- Hold the strongest voice within their domain:
  - **Cuby Inc. representative:** technical authority (code
    quality, API design, build system, performance, style)
  - **QSS Corp. representative:** domain authority
    (scientific correctness, conventions, reference data,
    use cases)
- May delegate their representative role to another person
  within their organization with notice to the other founder
- Cannot delegate their veto authority

### 3.3 Maintainers

Contributors granted merge authority over specific areas of
the project. Maintainers are not founders; they earn the role
through sustained, high-quality contributions. Detailed
criteria are in `governance/roles.md`.

In Phase 1, maintainers are appointed by the project lead with
founder consultation. In Phase 2+, maintainers are appointed
by the TSC.

### 3.4 Contributors

Anyone who has had a contribution merged into a QSSL
repository. Contributors are listed in the GitHub contributors
graph of each repository and in the `AUTHORS`/`CONTRIBUTORS`
files (when populated).

There are no formal requirements to be a contributor beyond
having a merged PR. There is no "contributor agreement" beyond
the DCO sign-off (see `policies/licensing-and-cla.md`).

### 3.5 Working group leads (any phase)

Working groups can be formed at any time — including during
Phase 1 — around focused scientific or technical areas. Each
working group has a lead who coordinates the group's work. In
Phase 1, working group leads report to the project lead; in
Phase 2+, they report to the TSC. Working group rules are
detailed in `governance/working-groups.md`.

## 4. Decision-Making

### 4.1 The default process

The default process for any non-trivial decision is:

1. **Proposal.** A contributor opens a proposal. For
   significant changes, this is a PR to `Team/proposals/`.
   For smaller changes, it may be a GitHub Issue, a
   GitHub Discussion, or a Discord thread.
2. **Discussion.** The proposal is discussed in the
   appropriate venue. A minimum 7-day public comment
   period is required for charter-level or governance-
   level changes. For technical changes, the comment
   period should be "long enough for active contributors
   to respond" — usually 3–14 days, depending on impact.
3. **Decision.** The body with authority makes a decision.
   For Phase 1, this is the project lead (with founder
   consultation, or with founder veto on charter matters).
4. **Recording.** The decision is recorded. Charter-level
   and governance-level decisions become ADRs in
   `Team/decisions/`. Technical decisions are recorded
   via merged PRs, with the PR description serving as
   the rationale.

Decisions are recorded in public, even when made
unanimously. There are no closed-door decisions in
governance or scope matters.

### 4.2 Decision authority matrix

The decision authority matrix is in CHARTER §7. The
high-level summary:

| Decision type | Phase 1 authority | Phase 2+ authority |
|---|---|---|
| Day-to-day operations | Project lead | TSC |
| Architecture changes | Project lead + founder consultation | TSC majority |
| Scientific conventions | QSS Corp. representative (domain authority) | TSC, with domain input |
| Engineering standards | Cuby Inc. representative (technical authority) | TSC, with technical input |
| Adding/removing modules | Project lead | TSC |
| Breaking API changes | Project lead + founder consultation | TSC supermajority (≥⅔) |
| Releases | Project lead | TSC |
| Charter amendments | Both founders (veto) | TSC unanimous + founder ratification |
| Governance doc amendments | Project lead + both founder representatives (founder veto held) | TSC (founder veto on governance amendments ends with Phase 1, by design) |
| Maintainer appointment/removal | Project lead | TSC |
| CoC enforcement | Project lead + co-opted reviewers | TSC-enforced process |
| Project-lead succession | Both founders | TSC + founders |
| Transfer to foundation | Both founders | TSC + founders |
| Logo / trademark changes | QSS Corp. representative (per CHARTER §6.1) | QSS Corp. (policy persists) |

### 4.3 Domain-vs-engineering conflict resolution

When a domain decision and an engineering decision conflict,
the principle from CHARTER §5.1 applies:

> Scientific correctness is non-negotiable; engineering
> choices are negotiable.

In practice this means:

- If QSS Corp. (domain) says a particular convention must be
  followed for scientific reasons, the engineering side
  accommodates it.
- If Cuby Inc. (technical) says a particular API design
  pattern is required for engineering reasons, the domain
  side accommodates it *only* if the pattern does not
  compromise scientific correctness.
- Genuinely cross-cutting conflicts (e.g., a feature that
  is scientifically correct but breaks the public API in
  an unsupportable way) escalate to the project lead, and
  if unresolved there, to both founders in Phase 1 or to
  the TSC in Phase 2+.

### 4.4 Urgent decisions

Not all decisions can wait for a 7-day comment period. The
project lead (Phase 1) or TSC chair (Phase 2+) may make
**urgent decisions** when:

- A security vulnerability is being actively exploited
- A release is blocked and the block is causing user harm
- A CoC violation requires immediate action
- An external event (legal, funding, infrastructure) requires
  same-day response

Urgent decisions are made, acted upon, and then immediately
documented in a public post-mortem within 7 days. The
default is: **act, then explain, then revise if needed.**
Reversing a bad urgent decision is cheap; missing a real
emergency is expensive.

### 4.5 Reversing decisions

Decisions can be reversed. The process is the same as the
process that made the original decision, but expedited: a
new proposal is opened, the prior decision is referenced and
critiqued, and the new proposal is decided on its merits.

Reversing a decision does not require unanimous agreement
unless the original decision itself required unanimity
(e.g., charter amendments).

## 5. Conflict Resolution

Conflict is normal and expected in any active project. The
goal is not to avoid conflict but to handle it well.

### 5.1 Technical disagreements

Most disagreements are technical. They are resolved through:

1. **Evidence.** Cite the data, the spec, the test, the
   benchmark, the published literature. Opinions are fine;
   opinions backed by evidence are better.
2. **Domain authority.** When a question of scientific
   correctness arises, the QSS Corp. representative
   (Phase 1) or domain-expert TSC member (Phase 2+) has
   the strongest voice, subject to the principle in
   §4.3.
3. **Escalation.** If technical disagreement cannot be
   resolved at the working group or maintainer level, it
   escalates to the project lead (Phase 1) or TSC
   (Phase 2+).

### 5.2 Personal or community conflicts

When conflict becomes personal, or when a community member
feels harassed, dismissed, or attacked, the CoC applies.
`CODE_OF_CONDUCT.md` describes the expected behavior and the
enforcement process. The project lead (Phase 1) or a
designated TSC member (Phase 2+) handles enforcement, with
co-opted reviewers as needed for impartiality.

### 5.3 Governance disputes

When a dispute is *about governance itself* — e.g., "this
rule is unfair", "the project lead is overstepping", "the
founder veto is being abused" — the dispute is handled by:

1. **Internal discussion.** The disputants and the relevant
   decision-makers attempt to resolve it through direct
   conversation in a public channel.
2. **Founder consultation.** If internal discussion fails,
   the matter is raised with both founder representatives
   (Phase 1) or escalated to the TSC minus any
   conflicted members (Phase 2+).
3. **Final resolution.** In Phase 1, the founders have
   final say on governance disputes. In Phase 2+, the
   TSC minus conflicted members has final say, subject
   to founder veto on charter-level matters.

A disputant who is unsatisfied with a governance decision
has the right to:

- Document their objection publicly in a `decisions/`
  ADR
- Appeal to the next-higher body in the structure
- Fork the project under the Apache-2.0 license (this is
  a right of every licensee and not something that
  requires anyone's permission)

The last option is the ultimate safety valve. The project
exists to serve its users and contributors; if it fails to
do so, forking is a legitimate response.

## 6. Maintainer Lifecycle

### 6.1 Becoming a maintainer

Maintainers are contributors who have demonstrated sustained,
high-quality contributions and judgment. There is no fixed
formula; the project lead (Phase 1) or TSC (Phase 2+) makes
the call. Indicators include:

- Multiple substantial merged PRs
- Code review activity (reviewing others' PRs)
- Triage activity (managing issues, labeling, closing
  duplicates)
- Scientific or domain expertise relevant to a module
- Helpful, respectful behavior in community channels

A contributor is not entitled to maintainer status based on
contribution count alone. A maintainer is entrusted with
judgment, not just code.

### 6.2 Maintainer responsibilities

A maintainer is expected to:

- Review PRs in their area within a reasonable time
  (target: first response within 7 days; merge or close
  within 30 days unless there is good reason otherwise)
- Triage issues in their area
- Participate in major decisions affecting their area
- Uphold the CoC
- Communicate proactively when they will be unavailable
  for an extended period

A maintainer who is inactive for 6+ months is gently
stepped down (see §6.3) and can be re-appointed when
active again.

### 6.3 Stepping down

A maintainer may step down at any time, for any reason.
Stepping down is not a failure; it is a normal part of
project life. The process is:

- The maintainer informs the project lead (Phase 1) or
  TSC (Phase 2+)
- The maintainer's areas of responsibility are
  redistributed
- The maintainer's name is moved to a "past maintainers"
  list (if one is maintained)

Stepping down is reversible: a past maintainer can be
re-appointed to the same or different areas when their
availability returns.

### 6.4 Removal

A maintainer may be removed for:

- Sustained inactivity (per §6.2)
- CoC violations
- Conduct that materially harms the project (e.g.,
  malicious code, intentional breakage, abuse of
  authority)

Removal is not a casual process. It requires:

- A documented pattern of behavior, not a single incident
  (except in extreme cases)
- Discussion among the project lead and founder
  representatives (Phase 1) or TSC minus the affected
  member (Phase 2+)
- A clear, written reason communicated to the affected
  maintainer
- A public summary in the `decisions/` log (with
  personally-identifying details redacted if the matter
  was a CoC enforcement action)

A removed maintainer retains all rights of any other
contributor (including the right to submit PRs) but loses
maintainer privileges (merge authority, repository write
access).

## 7. Working Groups (high-level)

Working groups are formed around focused scientific or
technical areas (e.g., cosmology, celestial mechanics,
imaging, core infrastructure). **Working groups can be
established in any phase, including Phase 1** — there is
no requirement to wait for Phase 2 or TSC formation.

Each working group has:

- A Discord channel and role
- A GitHub team
- A working group lead who coordinates the group's work
  and reports to the project lead (Phase 1) or the TSC
  (Phase 2+)
- Its own subset of issues, PRs, and discussion

Working groups **inherit** QSSL's overall governance. They
do not have their own governance, their own code of
conduct, or their own release authority. A working group
that wants to do something outside the inherited governance
(e.g., publish independently, accept funding, partner
externally) must escalate to the project lead (Phase 1) or
the TSC (Phase 2+).

Detailed working group rules — formation, leadership
selection, dissolution, scope discipline — are in
`governance/working-groups.md`.

## 8. Communication

| Channel | Purpose | Authority |
|---|---|---|
| Discord | Synchronous chat, working group coordination, quick questions | Working group leads and project lead |
| GitHub Issues | Bug reports, feature requests, scientific corrections | Maintainers |
| GitHub Discussions | Open-ended ideas, design exploration, community conversation | All |
| Pull Requests | Code, documentation, and design changes | Maintainers (merging); all (reviewing) |
| `Team/proposals/` (PRs) | Formal RFCs for significant decisions | Project lead / TSC |
| `Team/decisions/` (merged) | Architecture Decision Records (ADRs) | All (read), project lead / TSC (write) |
| Direct messages | Coordination of non-controversial work | Acceptable. Decisions are *not* made in DMs. |

The last line is important: **decisions are not made in DMs.**
If a decision needs to be made, it goes through the public
process. DMs are for coordination, not governance.

## 9. Phase Transitions

The criteria for moving between phases are in CHARTER §5.3.
The procedure is:

### 9.1 Phase 1 → Phase 2

1. The QSS Corp. steering committee overseeing QSSL
   determines that the library has reached sufficient
   maturity, community engagement, and maintainer depth.
2. The QSS Corp. steering committee communicates this
   decision to the Cuby Inc. representative and the
   project lead, with a written rationale.
3. The TSC is formed, with both founder representatives
   plus 1–3 elected external maintainers. (Maintainer
   elections are managed by the project lead, with
   founder oversight.)
4. The TSC's first act is to ratify the existing
   governance, standards, and policies (which carry
   forward from Phase 1) and to publish a `decisions/`
   ADR recording the transition.
5. From this point, the TSC is the operational governing
   body.

### 9.2 Phase 2 → Phase 3

1. The TSC and founders jointly determine that the
   project has reached institutional adoption, sustained
   funding need, or community demand sufficient to
   warrant foundation hosting.
2. A fiscal host is selected (e.g., NumFOCUS, Open
   Source Collective, or a dedicated QSSL foundation).
3. The project's legal and financial assets (if any) are
   transferred to the fiscal host.
4. The TSC continues as the technical governing body,
   now reporting to the foundation board for legal and
   financial matters.
5. Founder representatives transition from "stewardship"
   to "sponsorship" roles.

### 9.3 Reversing a phase transition

A phase transition can be reversed if the new structure
is not working. For example, if the TSC becomes
dysfunctional, the founders can dissolve it and return
to a Phase-1-style founder-led structure while a new
TSC is formed. This is exceptional and requires the
same level of agreement as the forward transition.

## 10. Cross-References

- `CHARTER.md` — mission, scope, non-goals, identity
- `governance/sponsorship.md` — Cuby Inc. ↔ QSS Corp.
  founding agreement (including project-lead
  designation process)
- `governance/roles.md` — detailed role definitions
- `governance/evolution.md` — phase transitions in
  detail
- `governance/working-groups.md` — working group rules
- `governance/decision-making.md` — detailed decision
  processes (Phase 2)
- `governance/conflict-resolution.md` — detailed
  conflict-resolution procedures (Phase 2)
- `CODE_OF_CONDUCT.md` — community standards and
  enforcement
- `CONTRIBUTING.md` — how to contribute
- `policies/licensing-and-cla.md` — DCO and
  corporate-contributions policy
- `decisions/` — ADRs (Architecture Decision Records)

## 11. Decision Log

| Version | Date | Summary | Authority |
|---|---|---|---|
| 1.0 | 2026-08-08 | Initial governance document. Defines Phase 1 founder-led structure (project lead, founder representatives, QSS Corp. steering committee), roles summary, default decision-making process, conflict-resolution procedures, maintainer lifecycle, working-group overview, communication channels, and phase-transition procedures. | Both founding stewards |

---

*This document is operational governance. It is expected to be
revised as the project grows and as Phase 2 / Phase 3 are
reached. The most reliable statement of how QSSL is run is
always the latest version of this file in the repository.*
