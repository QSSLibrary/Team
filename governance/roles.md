# QSSL Roles

> Detailed definition of every role in the QSSL project:
> responsibilities, authority, lifecycle, and conflict-of-interest
> rules. The charter defines what QSSL is; governance defines how
> it is run; this document defines who does what.
>
> **Status:** Active
> **Version:** 1.0
> **Effective date:** 2026-08-08
> **Supersedes:** none
> **Amends:** none
> **Authoritative copy:** this file at `governance/roles.md` in
> the `QSSLibrary/Team` repository

---

## 1. Purpose and Scope

This document defines the roles in the QSSL project in detail.
For each role, it specifies:

- The role's purpose
- The role's responsibilities
- The role's authority and decision-making power
- How a person enters the role (designation, election,
  promotion)
- How a person leaves the role (term, succession, removal)
- Conflict-of-interest rules for the role

Other documents reference these roles and summarize them
from different angles:

- `CHARTER.md` — high-level stewardship model
- `GOVERNANCE.md` — operational governance
- `governance/sponsorship.md` — the Cuby Inc. ↔ QSS Corp.
  relationship
- `governance/working-groups.md` — working group rules

In the event of a conflict between this document and any
other, this document prevails for role-specific questions.

## 2. Role Overview

| Role | Phase(s) | Authority | Selection | Term |
|---|---|---|---|---|
| Project lead | 1 (only) | Day-to-day operations | Mutual agreement of founders | Until successor designated |
| Founder representative (Cuby Inc.) | 1+ | Technical authority + charter-level veto | Designated by Cuby Inc. | Until replaced |
| Founder representative (QSS Corp.) | 1+ | Domain authority + charter-level veto | Designated by QSS Corp. | Until replaced |
| QSS Corp. steering committee | 1+ | Phase 2 transition decision | Designated by QSS Corp. | Until reorganized |
| Maintainer | 1+ | Merge authority in specific areas | Project lead (Phase 1) or TSC (Phase 2+) | Until stepping down or removal |
| Working group lead | Any | Coordination of a working group | Project lead (Phase 1) or TSC (Phase 2+) | Until stepping down or removal |
| Working group member | Any | Participation in a working group's work | Self-selection + WG lead acceptance | Until leaving the WG |
| TSC member | 2+ | Operational decisions | TSC formation (Phase 2) | Until stepping down or removal |
| Foundation board | 3+ | Legal, financial | Phase 3 transition | Per foundation bylaws |
| Contributor | Any | Submit PRs, comment, vote (if applicable) | Implicit (any merged PR) | Indefinite |

Phase 1 designations are recorded in §11.1 of
`governance/sponsorship.md`.

## 3. Project Lead (Phase 1 only)

### 3.1 Purpose

The project lead is the operational head of QSSL in
Phase 1. They are the public face of the project and the
person who makes day-to-day decisions.

### 3.2 Responsibilities

- Make day-to-day operational decisions (release timing,
  PR merges, issue triage, infrastructure)
- Coordinate with the founder representatives on
  significant decisions
- Coordinate with working group leads
- Maintain project documentation and ADRs
- Prepare releases
- Represent the project in external contexts (e.g.,
  conferences, partnerships)
- Uphold the code of conduct

### 3.3 Authority

- Final say on operational decisions, subject to founder
  consultation
- Final say on routine PR merges
- Authority to call urgent decisions (per `GOVERNANCE.md`
  §4.4) in time-sensitive situations
- Authority to designate and remove maintainers
  (subject to founder consultation)

### 3.4 Limitations

- Cannot make charter-level decisions unilaterally (both
  founders have veto)
- Cannot make governance-level decisions unilaterally
  (both founders have veto)
- Cannot amend this document or `CHARTER.md` without
  founder approval
- Cannot transfer the project to a fiscal host without
  founder approval
- Cannot remove a founder representative
- Cannot unilaterally make decisions about their own
  role (e.g., compensation, scope of authority) — such
  decisions go to the founders

### 3.5 Designation

The Phase 1 project lead is **[Ramtin Kosari](github.com/ramtinkosari)**. Designation is by mutual agreement of
both founding stewards and is recorded in
`governance/sponsorship.md` §5.1.

### 3.6 Term

There is no fixed term. The project lead serves at the
pleasure of the founding stewards. The succession
procedure is in `governance/sponsorship.md` §5.3.

### 3.7 Removal

Removal is governed by `governance/sponsorship.md` §5.4
and requires unanimous founder agreement. Removal is
reserved for sustained failure, CoC violations, or
conduct that materially harms the project.

### 3.8 Conflict of interest

The project lead is also currently a founder
representative and a QSS Corp. steering committee
member. When a decision involves a personal interest of
the project lead, the project lead must:

- Disclose the personal interest at the start of
  discussion
- Recuse themselves from the decision if the personal
  interest is direct and material
- Allow the other founder representative (and, in
  Phase 1, since both founder representatives are
  currently the same person, the project's external
  advisors if any) to make the decision in their place

In Phase 1, with all three roles held by one person,
the practical effect of COI rules is limited. The
project lead is expected to apply the rule in spirit
by deferring to outside input (e.g., a maintainer, an
external advisor, or the broader community) on
decisions where their personal stake is direct.

## 4. Founder Representatives

### 4.1 Purpose

Each founding steward designates one person to be its
founder representative on the QSSL project. Founder
representatives hold charter-level and governance-level
veto authority in Phase 1 and continue as TSC members
in Phase 2+.

### 4.2 Cuby Inc. founder representative (technical authority)

**Phase 1 designation:** **[Ramtin Kosari](github.com/ramtinkosari)**.

Authority over:

- Code architecture, organization, and design patterns
- C++ version floor and compiler support matrix
- API design conventions
- Code style, formatting, tooling
- Build system, packaging, distribution
- Testing strategy and CI/CD infrastructure
- Performance engineering
- Documentation tooling

### 4.3 QSS Corp. founder representative (domain authority)

**Phase 1 designation:** **[Ramtin Kosari](github.com/ramtinkosari)**.

Authority over:

- Scientific domains covered (within `CHARTER.md` §3)
- Algorithms chosen for each domain
- Scientific conventions used (IAU, SOFA, IERS)
- Reference data and catalogs
- Coordinate systems, time scales, reference frames
- Numerical precision requirements per domain
- Validation against literature and reference
  implementations

### 4.4 Authority and veto

In Phase 1, founder representatives jointly hold:

- Veto on charter amendments
- Veto on governance doc amendments
- Veto on project-lead removal
- Veto on phase transitions
- Veto on the addition or removal of a maintainer
  (advisory; project lead decides, but founders
  may override)
- Veto on the appointment of a new founder
  representative (only the corresponding founder
  may appoint their own representative)

In Phase 2+, founder representatives continue as TSC
members but lose the unilateral veto on governance
amendments (which moves to the TSC majority). The
veto on charter amendments persists, conditioned on
TSC unanimous agreement.

### 4.5 Designation and replacement

Each founder may designate or replace its own founder
representative at any time, with notice to the other
founder. The change is recorded in a `decisions/` ADR
and reflected in this document and in
`governance/sponsorship.md` §3.

A founder representative may step down at any time, in
which case the corresponding founder designates a
replacement.

### 4.6 Term

There is no fixed term. Founder representatives serve
at the pleasure of their respective founding
organizations.

### 4.7 Removal

A founder representative may be removed only by their
respective founder. The removing founder designates a
replacement. The change is recorded as a `decisions/`
ADR.

### 4.8 Conflict of interest

When a decision involves the personal or business
interests of a founder representative's organization
beyond the normal scope of the QSSL project (e.g., a
decision that would disproportionately benefit one of
the founder's other products), the founder
representative must recuse from that decision. In
Phase 1, with both representatives being the same
person, the COI rule is best-effort and the project
lead is expected to seek outside input on the affected
decision.

## 5. QSS Corp. Steering Committee

### 5.1 Purpose

The QSS Corp. steering committee is an internal body
within QSS Corp. that holds the discretion to
determine when QSSL has reached sufficient maturity,
community engagement, and maintainer depth to
transition from Phase 1 to Phase 2 governance.

### 5.2 Phase 1 composition

The Phase 1 committee is a single-member body
comprising **Ramtin Kosari**. QSS Corp. may expand
the committee in the future; any such expansion is
recorded in a `decisions/` ADR.

### 5.3 Authority

- Sole discretion to determine when Phase 2 begins,
  per `CHARTER.md` §5.3 and `governance/evolution.md`
- Authority to make the Phase 2 transition effective
  (subject to written notice to the other founder and
  the project lead)

The committee has no other authority. It does not
make technical or domain decisions; those are the
province of the QSS Corp. founder representative.

### 5.4 Operation

The committee operates by QSS Corp.'s internal
procedures. Its Phase 2 transition decision is
communicated in writing to Cuby Inc. and the project
lead.

### 5.5 Conflict of interest

The committee is internal to QSS Corp. and is
accountable to QSS Corp. alone. There is no
external COI procedure. The committee is expected to
exercise its Phase 2 discretion in good faith, with
the project's interest as its primary consideration.

## 6. Maintainers

### 6.1 Purpose

Maintainers are contributors who have been granted
merge authority over specific areas of the project.
They are the operational backbone of the codebase.

### 6.2 Areas of responsibility

A maintainer's "area" is typically a module, a
subsystem, or a specific concern:

- A specific QSSL module (e.g., coordinate systems,
  celestial mechanics)
- A cross-cutting concern (e.g., documentation, CI,
  packaging)
- A specific platform or compiler (e.g., Windows
  build, ARM support)

Areas are assigned at the time of maintainer
appointment and may be revised later as the project's
structure evolves.

### 6.3 Responsibilities

A maintainer is expected to:

- Review PRs in their area within a reasonable time
  (target: first response within 7 days; merge or
  close within 30 days)
- Triage issues in their area
- Participate in decisions affecting their area
- Uphold the code of conduct
- Communicate proactively about extended unavailability
- Mentor contributors in their area

### 6.4 Authority

- Merge authority over PRs in their area (subject to
  the project lead's or TSC's overall authority)
- Ability to label, close, and prioritize issues in
  their area
- Vote in maintainer elections (when such elections
  exist)
- Participate in TSC formation (in Phase 2)

### 6.5 Promotion criteria

Maintainers are promoted from contributors based on
demonstrated sustained, high-quality contribution.
There is no fixed formula. Indicators include:

- Multiple substantial merged PRs
- Code review activity
- Triage activity
- Scientific or domain expertise
- Helpful, respectful community behavior
- Trust demonstrated through judgment calls

The project lead (Phase 1) or TSC (Phase 2+) makes
the call. A contributor is not entitled to maintainer
status based on contribution count alone.

### 6.6 Stepping down

A maintainer may step down at any time, for any
reason, with notice to the project lead (Phase 1) or
TSC (Phase 2+). Their areas of responsibility are
redistributed. Stepping down is reversible.

### 6.7 Removal

A maintainer may be removed for:

- Sustained inactivity (6+ months with no engagement)
- CoC violations
- Conduct that materially harms the project

Removal requires:

- A documented pattern (except in extreme cases)
- Discussion among the project lead and founder
  representatives (Phase 1) or TSC minus the affected
  member (Phase 2+)
- A written reason communicated to the affected
  maintainer
- A public summary in `decisions/` (with personal
  details redacted if the matter was a CoC action)

A removed maintainer retains all rights of any other
contributor but loses maintainer privileges.

### 6.8 Conflict of interest

A maintainer must recuse from decisions where they
have a direct personal or financial interest. For
example, a maintainer who is also a paid consultant
to a downstream user of QSSL should recuse from
decisions that would benefit that user in a way not
shared by the broader user base.

## 7. Working Group Leads

### 7.1 Purpose

Working group leads coordinate the work of a working
group. They are the WG's public face and the person
accountable to the project lead (Phase 1) or TSC
(Phase 2+) for the WG's progress.

### 7.2 Selection

A working group lead is selected by the project lead
(Phase 1) or TSC (Phase 2+) when the working group
is formed. The lead is typically a person who
proposed the WG or who has demonstrated the
relevant scientific or technical expertise and
organizational capacity.

### 7.3 Responsibilities

- Coordinate the WG's work (issues, PRs, discussions)
- Set the WG's short-term priorities within its
  scope
- Report to the project lead or TSC periodically
- Onboard new WG members
- Uphold the code of conduct within the WG
- Surface scope-disputes to the project lead or TSC

### 7.4 Authority

- Authority over the WG's day-to-day operations
- Authority to assign WG-internal tasks
- Authority to recommend contributors to maintainer
  status (for their area)
- Authority to call WG meetings

The lead does **not** have authority to:

- Make decisions binding on QSSL beyond the WG
- Modify the WG's scope (scope changes go to the
  project lead or TSC)
- Speak on behalf of QSSL in external contexts

### 7.5 Term and removal

A working group lead serves at the pleasure of the
project lead (Phase 1) or TSC (Phase 2+). The lead
may step down at any time. Removal follows the same
process as maintainer removal (§6.7).

### 7.6 Conflict of interest

Same rules as maintainers (§6.8).

## 8. Working Group Members

### 8.1 Purpose

Working group members are contributors who have
joined a specific working group. They are typically
focused on the WG's scientific or technical area.

### 8.2 Joining a working group

- Self-selection: a contributor can join any working
  group by expressing interest in the WG's Discord
  channel, GitHub team, or in a relevant issue/PR
- WG lead acceptance: the WG lead may accept or
  decline new members based on the WG's capacity
  and the member's interest
- No formal application is required

### 8.3 Responsibilities

- Participate in the WG's discussions and work
- Follow the WG's coordination conventions
- Uphold the code of conduct

There is no minimum activity level. A working group
member may participate as their time and interest
allow.

### 8.4 Authority

- Authority to submit PRs and issues in the WG's
  area
- Authority to participate in WG decisions
- Authority to leave the WG at any time

A working group member does not have maintainer
privileges in the WG's area unless separately
appointed as a maintainer.

### 8.5 Leaving a working group

A working group member may leave at any time, with
or without notice. The WG lead may ask a member to
leave if the member's behavior is disruptive, but
this is unusual and a CoC matter if serious.

## 9. Contributors

### 9.1 Purpose

A contributor is anyone who has had a contribution
merged into a QSSL repository. Contributors are the
broadest role in the project and have no formal
obligations.

### 9.2 Becoming a contributor

- Submit a PR to any QSSL repository
- Have the PR reviewed and merged
- You are now a contributor

There is no formal application, no DCO check at
membership time (the DCO is checked per-commit), and
no fee.

### 9.3 Authority

- Submit PRs, issues, and discussions
- Comment on others' PRs and issues
- Vote in community polls (when such polls exist)
- Run for maintainer (when such elections exist)
- Form a working group (subject to working-groups.md)

### 9.4 Obligations

- Sign off on commits (DCO)
- Uphold the code of conduct
- No other obligations

### 9.5 Leaving

A contributor's status is permanent. There is no
"leaving" the contributor role. A contributor who
becomes inactive remains a contributor.

## 10. TSC Members (Phase 2+)

### 10.1 Purpose

The Technical Steering Committee (TSC) is the
operational governing body in Phase 2 and beyond. It
takes over day-to-day decision authority from the
project lead and founder representatives.

### 10.2 Composition (Phase 2)

- Both founder representatives (continuing from Phase 1)
- 1–3 external maintainers elected by the maintainer
  body

Total: 3–5 members. The TSC may expand up to 7
members in Phase 3 or beyond.

### 10.3 Selection

- Founder representatives: continuing from their
  Phase 1 roles
- External TSC members: elected by the maintainer
  body. The election procedure is documented in
  `governance/evolution.md`.

### 10.4 Responsibilities

- Make operational decisions
- Maintain project quality and direction
- Appoint and remove maintainers
- Make release decisions
- Manage working groups
- Surface charter-level decisions to the founders
  (for ratification)

### 10.5 Authority

- Simple majority for routine decisions
- Supermajority (≥⅔) for breaking API changes
- Unanimous for charter amendments (subject to
  founder ratification)

### 10.6 Term

TSC members serve 2-year terms. They may serve
multiple consecutive terms. There is no fixed limit
on total terms.

### 10.7 Stepping down and removal

Same procedures as maintainers (§6.6, §6.7), with
the body that makes the removal decision being the
TSC minus the affected member (for external members)
or the founders (for founder representatives).

### 10.8 Conflict of interest

Same rules as maintainers (§6.8), plus: an external
TSC member who is also a maintainer in a specific
area must recuse from decisions in that area where
their role as maintainer creates a conflict with
their role as TSC member (e.g., appeals of their
own maintainer decisions).

## 11. General Conflict of Interest Rules

These rules apply to all roles unless a specific role
section says otherwise.

### 11.1 Disclosure

A role-holder with a direct personal or financial
interest in a decision must disclose that interest
at the start of any discussion of the decision. The
disclosure is recorded in the relevant `decisions/`
ADR.

### 11.2 Recusal

A role-holder with a direct personal or financial
interest in a decision must recuse from the
decision itself. Recusal means:

- Not voting on the decision
- Not blocking consensus
- Not making public statements about the decision
  except to explain the recusal
- Allowing the decision to proceed without their
  participation

### 11.3 Decisions affecting the role-holder's own role

A role-holder must recuse from any decision that
affects their own role's authority, scope, or
compensation. Such decisions are made by the
next-higher body (e.g., the founders for the
project lead, the TSC for maintainers).

### 11.4 Decisions affecting the role-holder's employer

A role-holder whose employer has a direct interest
in a decision must recuse, even if the
role-holder personally does not. For example, a
maintainer employed by a downstream user of QSSL
must recuse from decisions that would benefit that
user in a way not shared by the broader user base.

### 11.5 No implicit authority

A role-holder's authority does not extend to
matters outside their role. For example, a working
group lead does not have maintainer authority; a
maintainer does not have TSC authority. Authority
attaches to roles, not to individuals.

## 12. Cross-References

- `CHARTER.md` — high-level stewardship model
- `GOVERNANCE.md` — operational governance
- `governance/sponsorship.md` — Cuby Inc. ↔ QSS Corp.
  agreement
- `governance/working-groups.md` — working group rules
- `governance/evolution.md` — phase transitions
- `CODE_OF_CONDUCT.md` — community standards
- `CONTRIBUTING.md` — how to contribute
- `policies/licensing-and-cla.md` — DCO and
  corporate-contributions policy

## 13. Decision Log

| Version | Date | Summary | Authority |
|---|---|---|---|
| 1.0 | 2026-08-08 | Initial roles document. Defines all roles (project lead, founder representatives, QSS Corp. steering committee, maintainers, working group leads, working group members, contributors, TSC members) with their responsibilities, authority, lifecycle, and conflict-of-interest rules. Phase 1 designations: project lead and both founder representatives and the QSS Corp. steering committee are all [Ramtin Kosari](github.com/ramtinkosari). | Project lead |

---

*This document is the canonical reference for QSSL roles. It
is expected to be amended as new roles are added or existing
roles evolve. The most reliable statement of any role's
definition is always the latest version of this file in the
repository.*
