# Cuby Inc. ↔ QSS Corp. Founding Sponsorship Agreement

> The internal agreement between the two founding stewards of QSSL.
> Defines how Cuby Inc. and QSS Corp. relate to each other and to
> the project, including their distinct authorities, the project
> lead designation, and the procedures for handling disagreements.
>
> **Status:** Active
> **Version:** 1.0
> **Effective date:** 2026-08-08
> **Supersedes:** none
> **Amends:** none
> **Authoritative copy:** this file at `governance/sponsorship.md`
> in the `QSSLibrary/Team` repository

---

## 1. Purpose

This document records the agreement between **Cuby Inc.** and
**QSS Corp.** regarding their joint stewardship of the QSSL
project. It exists to:

- Make the relationship between the two founding stewards
  explicit and durable
- Prevent ambiguity about roles, authorities, and
  decision-making
- Provide a written reference that future maintainers
  (and future generations of stewards) can consult
- Establish procedures for handling disagreements between
  the founders

This is **not** a legal contract between Cuby Inc. and
QSS Corp. as legal entities. It is a *governance* document
that records the public commitment of both organizations
to the project and to each other. The legal structure of
the relationship, if any, is handled separately.

## 2. Parties

The two parties to this agreement are:

- **Cuby Inc.** — a technology company. Founder representative:
  (to be designated by Cuby Inc. and recorded in §3.2 of
  this document when appointed).
- **QSS Corp.** — a space exploration company. Founder
  representative: (to be designated by QSS Corp. and recorded
  in §3.3 of this document when appointed). The QSS Corp.
  steering committee overseeing QSSL is identified in §4.

The GitHub organization `QSSLibrary` is the project's
primary home. Cuby Inc. and QSS Corp. jointly administer
this organization in Phase 1, with administration transferring
to the TSC (Phase 2) or a fiscal host (Phase 3) at the
appropriate phase transition.

## 3. Roles

### 3.1 Joint stewardship

Both Cuby Inc. and QSS Corp. are **founding stewards** of
QSSL. They hold joint responsibility for:

- The project's overall direction and health
- The funding and infrastructure the project requires
- The appointment and (if necessary) removal of the
  project lead
- Charter-level decisions (each holds veto on such
  decisions in Phase 1)
- Decisions about phase transitions (Phase 1 → 2 and
  Phase 2 → 3)
- Approving significant changes to this document

Neither founder may act unilaterally on the above. Both
must agree.

### 3.2 Cuby Inc. — technical authority

Cuby Inc. is the **technical authority** of the project.
This means Cuby Inc. holds the strongest voice on
**how the library is built**:

- Code structure, architecture, and organization
- The C++ version floor and compiler support matrix
- API design conventions
- Code style, formatting, and tooling
- Build system, packaging, and distribution
- Testing strategy and CI/CD infrastructure
- Performance engineering and benchmarking practices
- Documentation structure and tooling

Cuby Inc. **does not** hold authority over scientific
correctness, scientific conventions, or domain-specific
decisions (see §3.3). Where engineering and domain
concerns conflict, see §6.2.

**Cuby Inc. founder representative** (Phase 1): **[Ramtin Kosari](github.com/ramtinkosari)**.

### 3.3 QSS Corp. — domain authority

QSS Corp. is the **domain authority** of the project.
This means QSS Corp. holds the strongest voice on
**what the library does** scientifically:

- The scientific domains QSSL covers (within the
  scope set by `CHARTER.md` §3)
- The algorithms chosen for each domain
- The scientific conventions used (e.g., IAU
  resolutions, SOFA reference data, IERS conventions)
- The reference data and catalogs used
- Coordinate systems, time scales, and reference frames
- Numerical precision requirements per domain
- Validation against published literature and reference
  implementations

QSS Corp. **does not** hold authority over engineering
decisions (see §3.2). Where domain and engineering
concerns conflict, see §6.2.

**QSS Corp. founder representative** (Phase 1): **[Ramtin Kosari](github.com/ramtinkosari)**.

### 3.4 Other projects of the founders

Both founders have other projects and business activities
outside QSSL, including:

- Cuby Inc.'s **Synestia-Studio** game studio
- QSS Corp.'s **IRC-ATL** amateur-astronomy research group
- Other projects not enumerated here

These projects are **users of QSSL**, not parts of QSSL's
governance. They reinforce the founders' stake in the
project's quality but are not channels through which
either founder can direct QSSL's technical or domain
decisions. (See also `CHARTER.md` §5.1.)

## 4. QSS Corp. Steering Committee

The QSS Corp. steering committee overseeing QSSL is the
internal body within QSS Corp. that holds the discretion
to determine when QSSL has reached sufficient maturity,
community engagement, and maintainer depth to transition
from Phase 1 to Phase 2 governance (see `CHARTER.md` §5.3
and `governance/evolution.md`).

**QSS Corp. steering committee composition** (Phase 1):
The Phase 1 committee is a single-member body, comprising
**Ramtin Kosari**. As the project grows and the
stakeholder base broadens, QSS Corp. may expand the
committee to include additional QSS Corp. personnel
or external advisors. Any such expansion is recorded
in a `decisions/` ADR.

The committee operates by QSS Corp.'s internal procedures.
It is not subject to Cuby Inc. veto, but its Phase 2
transition decision must be communicated in writing to
Cuby Inc. and the project lead before taking effect.

## 5. Project Lead

### 5.1 Designation (Phase 1)

The Phase 1 project lead is **[Ramtin Kosari](github.com/ramtinkosari)**. This designation is by mutual agreement
of Cuby Inc. and QSS Corp. and is recorded in this
document.

Ramtin Kosari is affiliated with both founding
organizations. In the project lead role, he represents
the *project*, not any single company. The role's
authorities and limitations are defined in
`GOVERNANCE.md` §3.1.

### 5.2 Responsibilities

In addition to the operational responsibilities listed
in `GOVERNANCE.md` §3.1, the project lead is responsible
to the founding stewards for:

- Communicating significant decisions in a timely
  manner
- Maintaining the project's public documentation
  (charter, governance, ADRs)
- Organizing phase-transition discussions when
  appropriate
- Upholding the code of conduct
- Acting as a public face of the project when needed

### 5.3 Successor designation

If Ramtin Kosari becomes unable or unwilling to continue
as project lead, the procedure is:

1. The project lead (or, if incapacitated, either
   founder) notifies both founders of the change.
2. The two founders confer to designate a successor.
   The successor must be acceptable to both founders.
3. If the two founders cannot agree on a successor
   within 60 days, the matter is referred to the
   conflict-resolution procedure (§7).
4. The successor's identity, GitHub handle, and effective
   date are recorded in a `decisions/` ADR and in
   `GOVERNANCE.md` §3.1.

There is no fixed term. The project lead serves at the
pleasure of the founding stewards, subject to the
succession procedure above.

### 5.4 Removal

The project lead may be removed by unanimous agreement
of both founders. Removal is reserved for:

- Sustained failure to perform the role's
  responsibilities
- Conduct that materially harms the project
- Violations of the code of conduct
- Loss of confidence by both founders

Removal is not a casual process. It requires:

- A documented pattern of behavior, not a single
  incident (except in extreme cases)
- Discussion between the two founders
- A clear, written reason communicated to the
  affected project lead
- A public summary in the `decisions/` log (with
  personally-identifying details redacted if the
  matter was a CoC enforcement action)

## 6. Decision-Making Between Founders

### 6.1 Categories of founder decisions

Decisions that require founder agreement fall into three
categories:

- **Charter-level decisions** (e.g., amending the
  charter, changing the project's mission or scope,
  transferring the project to a fiscal host) — require
  affirmative agreement of both founders; each holds
  veto authority.
- **Governance-level decisions** (e.g., changing this
  document, appointing or removing the project lead,
  governance doc amendments in Phase 1) — require
  affirmative agreement of both founders.
- **Operational decisions** (e.g., routine release
  planning, infrastructure choices, hiring of
  contractors) — are delegated to the project lead,
  with founder consultation on significant matters.

The decision authority matrix in `CHARTER.md` §7 and
`GOVERNANCE.md` §4.2 is authoritative for which decisions
fall into which category.

### 6.2 Domain vs. engineering conflict

When a question falls into both the domain authority of
QSS Corp. and the technical authority of Cuby Inc., the
principle from `CHARTER.md` §5.1 applies:

> Scientific correctness is non-negotiable; engineering
> choices are negotiable.

In practice this means:

- QSS Corp.'s domain decisions stand unless they
  require engineering choices that Cuby Inc. can show
  are technically infeasible or unsupportable.
- Cuby Inc.'s technical decisions stand unless they
  require scientific choices that QSS Corp. can show
  are incorrect.
- Cross-cutting conflicts (where both a domain and a
  technical issue exist) escalate to the project lead
  for mediation, and if unresolved, to both founders
  under the conflict-resolution procedure (§7).

### 6.3 Communication between founders

Founders are expected to:

- Maintain a private communication channel for
  governance matters (e.g., a shared repository of
  decisions, a private email thread, or a private
  Discord channel) that complements the project's
  public channels
- Hold at least one joint review of the project's
  status every 6 months in Phase 1
- Record any founder-level decision as a `decisions/`
  ADR (with confidential details redacted where
  appropriate)

## 7. Conflict Resolution Between Founders

If the two founders cannot agree on a governance-level
or charter-level decision, the matter is handled
**privately** through the following steps:

1. **Direct discussion.** The two founders attempt to
   resolve the disagreement through direct conversation,
   either in person or via their private communication
   channel.
2. **Mediation.** If direct discussion fails, a
   mutually-agreed third party mediates.
3. **Deferral.** If mediation fails, the disputed
   decision is deferred. The status quo is preserved
   until the dispute is resolved. The project does not
   stall because of founder disagreement; the project
   lead continues to handle operational decisions.
4. **External arbitration.** If all of the above fail
   and the matter is genuinely blocking the project,
   the founders may agree to binding arbitration by
   a mutually-acceptable neutral party (e.g., a
   respected member of the open-source community).
   This is exceptional and is itself a founder-level
   decision.

Founder disputes are not escalated to public channels.
The project community is not involved in resolving
disagreements between the founding stewards. This
preserves the founders' ability to deliberate
candidly and to disagree without performing the
disagreement in public. The community's role in
*operational* decisions (via PRs, issues, discussions)
is unaffected; only founder-internal disputes are
kept private.

The founders retain the right to disagree indefinitely
on charter-level matters, with the status quo preserved.
This is a feature, not a bug: it prevents either
founder from forcing the other to accept changes they
fundamentally oppose.

## 8. Withdrawal and Dissolution

### 8.1 Withdrawal of a founder

If one founder decides to withdraw its stewardship of
QSSL (e.g., because of a change in the company's
priorities, a corporate restructuring, or a fundamental
disagreement), the procedure is:

1. The withdrawing founder provides written notice to
   the other founder and the project lead, with a
   minimum 90-day notice period.
2. During the notice period, the parties attempt to
   find a successor steward (a new corporate sponsor
   or fiscal host) willing to take on the withdrawing
   founder's role.
3. If a successor is found, the project's
   organizational structure is updated to reflect
   the change, and the charter is amended to record
   the new stewardship.
4. If no successor is found, the project continues
   under the remaining founder, with the project lead
   continuing to handle operations. The project
   remains independent; it does not become "owned by"
   the remaining founder.

The withdrawing founder's contributions to date remain
under the Apache-2.0 license. The withdrawing founder
loses all governance roles (founder representative,
TSC seat, QSS Corp. steering committee role, etc.)
effective at the end of the notice period.

### 8.2 Dissolution of the project

If both founders agree that the project should be
dissolved, or if the project has been inactive for
more than 24 months and the founders do not commit
to reviving it, the procedure is:

1. The founders publish a public notice of intended
   dissolution, with a 90-day comment period.
2. During the comment period, the community may
   propose continuation under different stewardship
   (e.g., a fork, a new fiscal host, an individual
   maintainer). The founders consider such proposals
   in good faith.
3. If no continuation proposal is accepted, the
   project is archived. The repositories are
   preserved in read-only state. The documentation
   remains accessible. The project's history is
   preserved in git history and in the
   `decisions/` ADRs.

The project is **never silently deleted**. Even in
dissolution, the historical record is preserved.

## 9. Term and Review

This agreement is in effect from the effective date
above and continues until:

- It is superseded by a new version
- One or both founders withdraw (§8.1)
- The project is dissolved (§8.2)
- The project is transferred to a fiscal host or
  foundation (Phase 3), at which point the fiscal
  host's own governance takes precedence

This document is reviewed:

- At each phase transition (Phase 1 → 2, Phase 2 → 3)
- Every 2 years, or sooner if either founder
  requests
- Whenever either founder's circumstances change
  materially (e.g., leadership change, corporate
  restructuring)

## 10. Cross-References

- `CHARTER.md` — mission, scope, identity
- `GOVERNANCE.md` — operational governance
- `governance/roles.md` — role definitions
- `governance/evolution.md` — phase transitions in
  detail
- `governance/working-groups.md` — working group rules
- `CODE_OF_CONDUCT.md` — community standards
- `decisions/` — Architecture Decision Records

## 11. Decision Log

| Version | Date | Summary | Authority |
|---|---|---|---|
| 1.0 | 2026-08-08 | Initial founding agreement. Records the project lead designation (Ramtin Kosari), the technical/domain authority split between Cuby Inc. and QSS Corp., the QSS Corp. steering committee role, the decision-making process, the conflict-resolution procedure, and the withdrawal/dissolution procedures. Both founder representatives and the QSS Corp. steering committee are designated as Ramtin Kosari at execution time. Founder disputes are handled privately, not escalated to the public community. | Both founding stewards (jointly) |

### 11.1 Resolved items (recorded at execution time)

The following items, listed as open in the original
draft of this agreement, are recorded here at the
effective date:

- **§3.2 Cuby Inc. founder representative:** [Ramtin Kosari](github.com/ramtinkosari).
- **§3.3 QSS Corp. founder representative:** [Ramtin Kosari](github.com/ramtinkosari). Note: the same individual
  currently serves as both founder representatives.
  This is a Phase 1 expedient; the design anticipates
  that the representatives will diverge as the
  organizations grow and as the project transitions
  to Phase 2 governance.
- **§4 QSS Corp. steering committee composition:** a
  single-member body, comprising Ramtin Kosari. The
  committee may be expanded in the future.

The fact that all three roles are currently held by
one individual represents a **bus factor of one** in
Phase 1. This is acknowledged in the governance
design: the Phase 2 transition (governed by
`governance/evolution.md`) is specifically intended
to distribute decision authority beyond the founders
and to bring in external maintainers. Until Phase 2
is reached, the project's continuity depends on
Ramtin Kosari's continued availability; succession
provisions in §5.3 and §8 are designed to handle
this risk, but the risk is real.

---

*This document is a governance record. It is expected to be
revised as the project grows. The most reliable statement of
the Cuby Inc. ↔ QSS Corp. relationship is always the latest
version of this file in the repository.*
