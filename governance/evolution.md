# QSSL Governance Evolution

> Detailed procedures for transitioning between governance
> phases (Phase 1 → 2 → 3), for evolving the governance
> structure itself, and for handling contingencies during
> transitions. The charter sets the high-level policy; this
> document sets the operational procedure.
>
> **Status:** Active
> **Version:** 1.0
> **Effective date:** 2026-08-08
> **Supersedes:** none
> **Amends:** none
> **Authoritative copy:** this file at
> `governance/evolution.md` in the `QSSLibrary/Team` repository

---

## 1. Purpose and Scope

This document describes how QSSL's governance evolves over
time. It covers:

- The detailed procedure for the Phase 1 → Phase 2
  transition (founder-led → TSC-led)
- The detailed procedure for the Phase 2 → Phase 3
  transition (TSC-led → foundation-hosted)
- The procedure for reversing a transition if the new
  structure is not working
- The procedure for amending the governance itself
- Contingencies for edge cases (e.g., a founder leaving
  mid-transition)

The high-level policy is in `CHARTER.md` §5.3. The
operational governance bodies are in `GOVERNANCE.md`
§2 and §9. This document is the **how**; the others are
the **what** and **why**.

In the event of a conflict between this document and
`CHARTER.md`, the charter prevails. In the event of a
conflict with `GOVERNANCE.md`, this document prevails
for transition-specific questions.

## 2. The Three Phases (Recap)

| Phase | Trigger to enter | Decision body | Project lead role | TSC role | Foundation role |
|---|---|---|---|---|---|
| **1** | Initial state | Project lead + founder representatives | Active | Not yet formed | Not yet involved |
| **2** | QSS Corp. steering committee discretion | TSC (3–5 members: 2 founders + 1–3 external) | Dissolved | Active | Not yet involved |
| **3** | TSC + founders joint decision | TSC + foundation board | Dissolved | Active (technical) | Active (legal/financial) |

A more detailed comparison is in `GOVERNANCE.md` §2 and
in `ARCHITECTURE.md` §10.3.

## 3. Phase 1 → Phase 2 Transition

### 3.1 Trigger

The transition is triggered when the **QSS Corp. steering
committee overseeing QSSL** determines that the project
has reached a level of maturity, community engagement,
and maintainer depth sufficient to be actively continued
under a TSC/maintainer decision structure.

The criterion is a judgment call, not a numerical
threshold. As stated in `CHARTER.md` §5.3:

> *"The library can be maintained by the community
> without the founders holding primary control."*

In practice, this typically means:

- Multiple active maintainers exist (3+ is a rough
  guide, but not a hard threshold)
- The project has had at least one major release
  (suggesting the release process works)
- A working group structure has formed organically
  (suggesting distributed ownership of work)
- The project has external contributors (not just the
  founders and their direct colleagues)
- The founders believe the project would continue
  healthily under a TSC structure for at least
  12 months

None of these are hard requirements. The founders may
decide to transition earlier, later, or — if the project
remains essentially a founder-driven effort — not at all.

### 3.2 Pre-transition preparation

Once the QSS Corp. steering committee is *considering*
a transition (but before deciding), the following
preparation begins:

1. **Inform Cuby Inc.** The QSS Corp. steering committee
   notifies the Cuby Inc. founder representative of
   the intent to consider a transition. This is a
   courtesy; it is not a veto point, but the transition
   is healthier if both founders are aligned.
2. **Inventory active maintainers.** The project lead
   compiles a list of active maintainers — those with
   recent activity (in the last 6 months) in their
   areas. This is the pool from which external TSC
   members will be elected.
3. **Audit the governance docs.** The project lead
   reviews `CHARTER.md`, `GOVERNANCE.md`, and the
   supporting governance documents. Any required
   updates are drafted as proposals and merged before
   the transition.
4. **Draft the TSC election procedure.** A specific
   procedure for electing external TSC members is
   documented (see §3.4 below).
5. **Announce intent publicly.** A GitHub Discussion
   and Discord announcement informs the community
   that a Phase 2 transition is being prepared. A
   14-day comment period is opened for community
   input.

### 3.3 The transition decision

The QSS Corp. steering committee makes the formal
decision to transition. The decision:

- Is communicated in writing to the Cuby Inc. founder
  representative, with a written rationale
- Is announced publicly (GitHub Discussion + Discord)
- Becomes effective on a specific date, at least 30
  days after the announcement (to allow for TSC
  election)

The decision is **not** a veto point for Cuby Inc. in
the formal sense — QSS Corp. holds the discretion per
`CHARTER.md` §5.3. But Cuby Inc. may raise concerns,
and the founders are expected to seek alignment.

If the two founders fundamentally disagree about the
timing of the transition, the dispute is handled per
`governance/sponsorship.md` §7 (privately).

### 3.4 TSC formation

The TSC is formed by an election of external members
from the active maintainer pool.

**Election procedure (Phase 2 initial formation):**

1. **Eligibility.** Any active maintainer is eligible
   to be nominated as an external TSC member. The
   project lead is not eligible (they hold the
   project-lead role until the TSC is formed; after
   that, the project-lead role is dissolved).
2. **Nomination.** Maintainers self-nominate or are
   nominated by other maintainers. Nominations
   include a brief statement of qualifications.
3. **Campaign.** A 14-day public campaign period
   during which nominees may publish statements and
   the community may ask questions.
4. **Voting.** Each active maintainer has one vote
   per available external TSC seat. Voting is by
   ranked preference or simple choice, depending on
   the number of seats and nominees. The exact
   mechanism is decided by the project lead with
   maintainer input, with a bias toward simplicity.
5. **Tally.** The project lead tallies votes and
   announces results. The top N vote-getters are
   elected, where N is the number of available
   seats (1–3).
6. **Objections.** A 7-day objection period follows.
   Objections are raised in a public channel and
   considered by the project lead and founder
   representatives. Sustained, serious objections
   may invalidate an election result, requiring a
   re-vote.

**Founder seats.** The two founder representatives
are ex officio TSC members. They do not go through
the election process.

**Total TSC size at formation:** 2 (founders) + 1–3
(external) = 3–5 members.

### 3.5 First actions of the new TSC

On the effective date of the transition, the new TSC
takes over. Its first actions, in order:

1. **Elect a chair.** The TSC elects one of its
   members as chair. The chair is the TSC's public
   face and breaks ties. The chair is elected by
   majority vote.
2. **Ratify existing governance.** The TSC reviews
   the existing `CHARTER.md`, `GOVERNANCE.md`, and
   supporting documents. Unless amendments are
   needed, the TSC issues a public statement
   ratifying the existing governance as its
   starting point. This is recorded as a
   `decisions/` ADR.
3. **Dissolve the project-lead role.** With the TSC
   in place, the project-lead role is no longer
   needed. The project lead (if different from the
   founder representatives) transitions to a
   maintainer role or steps down.
4. **Confirm or appoint maintainers.** The TSC
   reviews the existing maintainer list and either
   confirms each maintainer or makes changes
   according to its judgment.
5. **Publish the transition ADR.** A comprehensive
   `decisions/` ADR records the transition: the
   date, the new TSC composition, the first
   actions, and links to all related proposals.

### 3.6 Post-transition review

Six months after the transition, the TSC conducts a
public review:

- Has the transition achieved its goal (community
  can run the project without founder primary
  control)?
- Are there issues with the new structure?
- Are adjustments needed?

The review is published as a `decisions/` ADR. The
review may result in amendments to governance
documents or in proposals to reverse the transition
(per §5).

## 4. Phase 2 → Phase 3 Transition

### 4.1 Trigger

The transition is triggered when the **TSC and the
two founders jointly determine** that the project has
reached a level of institutional adoption, sustained
funding need, or community demand that warrants legal
and financial independence.

The criterion is a judgment call, not a numerical
threshold. As stated in `CHARTER.md` §5.3:

> *"The project has reached institutional adoption,
> sustained funding need, or community demand that
> warrants legal and financial independence."*

In practice, this typically means:

- A fiscal sponsor (e.g., NumFOCUS, Open Source
  Collective) has expressed interest in hosting QSSL
- The project has institutional users (companies,
  research institutions) that would benefit from
  formal legal/financial infrastructure
- Funding sources (grants, sponsorships) are being
  pursued that require a fiscal host
- The community is large enough that direct fiscal
  administration by the TSC is impractical

### 4.2 Pre-transition preparation

Once a Phase 3 transition is being considered:

1. **Joint decision by TSC and founders.** This is
   the only phase transition that requires both the
   TSC and the founders to agree. The decision is
   documented in a `decisions/` ADR.
2. **Fiscal host identification.** The TSC identifies
   candidate fiscal hosts. Common options include:
   - **NumFOCUS** — a well-established fiscal
     sponsor for scientific open-source projects
     (e.g., astropy, Jupyter)
   - **Open Source Collective** — a fiscal host
     operated by Open Collective
   - **A dedicated QSSL foundation** — established
     specifically for the project (significant
     overhead; usually only for very large projects)
3. **Community consultation.** A 30-day public
   comment period is opened. The community's
   preferences among candidate fiscal hosts are
   gathered and considered.
4. **Legal review.** Both founders and the TSC
   obtain legal advice (as appropriate to their
   jurisdictions) on the implications of the
   transfer.
5. **Asset inventory.** The TSC compiles a list of
   project assets to be transferred: GitHub
   organizations, domain names, trademarks (e.g.,
   the QSSL logo, per `CHARTER.md` §6.1), any
   funding accounts, and any physical or digital
   infrastructure.

### 4.3 Fiscal host selection

The TSC selects a fiscal host based on:

- Alignment with QSSL's mission and values
- Track record with similar projects
- Cost structure (fiscal hosts typically charge
  5–10% of funds administered)
- Community preference (gathered in §4.2.3)
- Practical considerations (geographic presence,
  language, etc.)

The selection is recorded in a `decisions/` ADR.

### 4.4 Asset transfer

Once a fiscal host is selected, the transfer proceeds:

1. **Trademark transfer (if applicable).** The QSSL
   logo, owned by QSS Corp. per `CHARTER.md` §6.1,
   is licensed (not transferred) to the fiscal
   host or to a project-specific entity, with terms
   that preserve the project community's right to
   use the mark. The licensing terms are recorded
   in a `decisions/` ADR.
2. **GitHub organization transfer.** The
   `QSSLibrary` GitHub organization is transferred
   to a new owner, typically the fiscal host or a
   designated project entity.
3. **Domain transfer (if any).** Any domains owned
   by the project are transferred to the fiscal
   host.
4. **Funding account transfer.** Any bank accounts,
   PayPal/Stripe/Open Collective accounts, etc.
   are transferred to the fiscal host's
   administration.
5. **Documentation of the transfer.** A
   comprehensive `decisions/` ADR records every
   transfer, with the date, the parties, and the
   terms.

### 4.5 Foundation setup (if applicable)

If the chosen structure is a **dedicated QSSL
foundation** (rather than an existing fiscal host),
additional steps apply:

1. **Choose a legal form.** Common forms:
   - **501(c)(3) non-profit** in the United States
     (tax-exempt)
   - **CIC (Community Interest Company)** in the
     United Kingdom
   - **Stichting** (foundation) in the Netherlands
   - **Other forms** as appropriate to the
     jurisdiction
2. **Draft bylaws.** The foundation's bylaws
   document its structure, board, and operations.
   The bylaws must be consistent with QSSL's
   governance documents; where they conflict, the
   governance documents prevail.
3. **Initial board.** The foundation board is
   established. At least one founder representative
   is on the initial board; the rest are drawn
   from the TSC and the community.
4. **Registration.** The foundation is registered
   in the chosen jurisdiction. This step has
   significant legal and administrative overhead
   and is typically outsourced to a lawyer
   experienced in non-profit formation.

A dedicated foundation is a significant undertaking.
For most projects at QSSL's likely scale, an
existing fiscal host is the more practical choice.

### 4.6 Post-transition governance

After the transition, the TSC continues as the
technical governing body, now reporting to the
foundation board (or fiscal host) for legal and
financial matters. The founder representatives
transition from "stewardship" to "sponsorship" roles
(per `GOVERNANCE.md` §2.3).

The post-transition governance is documented in an
updated `GOVERNANCE.md` and recorded in a
`decisions/` ADR.

### 4.7 Trial Period (recommended)

A Phase 3 transition is a significant commitment.
To reduce the risk of a transition that proves
unsuitable, the recommended path is a **trial period**:
a defined window during which the transition is
operational but reversible.

#### 4.7.1 What the trial period is

During the trial period:

- Assets are transferred to the fiscal host or
  foundation as described in §4.4
- The foundation operates as if the transition is
  permanent
- A contractual **sunset clause** is in effect,
  allowing the original owners (the TSC and the
  founders) to reclaim the transferred assets if
  the arrangement is not working
- The TSC and founders make a final decision at the
  end of the trial period

The trial period is **strongly recommended** for
any first-time foundation transition. It is the
project's safety valve against a poorly-fitting
foundation arrangement.

#### 4.7.2 Duration

- Default duration: **18 months**
- Acceptable range: 12–24 months
- The exact duration is fixed at the time of the
  transition and recorded in a `decisions/` ADR

#### 4.7.3 Sunset clause

The sunset clause is a contractual provision drafted
with legal counsel at the time of the transition. It
specifies:

- The conditions under which the clause can be
  invoked
- The procedure for invoking it (notice period,
  decision authority, asset return procedure)
- The exact set of assets subject to return

A typical sunset clause allows the TSC and founders
jointly to invoke it if:

- The foundation materially breaches the terms of
  the asset transfer
- The foundation ceases to operate in a manner
  consistent with QSSL's charter
- The project community, by whatever voting
  mechanism is established, votes for reversal
- A regulator or court orders dissolution or
  transfer

The sunset clause is recorded in the same
`decisions/` ADR that records the Phase 3
transition.

#### 4.7.4 End-of-trial decisions

At the end of the trial period, the TSC and founders
jointly make one of three decisions:

1. **Formalize the transition.** Remove the sunset
   clause. The transition becomes permanent. This
   is the expected outcome if the arrangement is
   working.
2. **Extend the trial.** Extend the trial period by
   6–12 months, with the sunset clause still in
   effect. Used if the arrangement shows promise
   but needs more time to evaluate.
3. **Reverse the transition.** Invoke the sunset
   clause and return the assets to the original
   owners (or to a successor steward). The project
   returns to Phase 2 (or earlier) governance.
   The foundation is dissolved or the project
   relationship ends.

#### 4.7.5 When the trial period is not used

In rare cases, the TSC and founders may decide to
forego the trial period — for example, if the
foundation arrangement is a well-established pattern
(e.g., a mature fiscal host like NumFOCUS hosting a
similar project) and the legal advice is that a
trial period adds unnecessary complexity. In such
cases, the decision to forego the trial period
itself is recorded in a `decisions/` ADR with
justification.

## 5. Reversing a Phase Transition

A phase transition can be reversed if the new
structure is not working. This is exceptional but
provided for.

### 5.1 Reversing Phase 1 → 2

If the TSC structure is not working (e.g., the TSC
becomes dysfunctional, fails to make decisions, or
excludes critical voices), the transition can be
reversed. The procedure:

1. **Initiation.** Either:
   - A majority of the TSC votes to dissolve itself
   - Both founder representatives jointly call for
     dissolution
   - A petition of ⅔ of active maintainers calls
     for dissolution
2. **Public discussion.** A 14-day public comment
     period is opened.
3. **Decision.** The dissolution is approved by:
   - Both founder representatives (each has veto),
     OR
   - Unanimous TSC minus any conflicted members
4. **Transition back to Phase 1.** The project
   returns to founder-led governance. A new project
   lead is designated (typically one of the
   founders). A new TSC will be formed when the
   conditions of §3.1 are again met.

### 5.2 Reversing Phase 2 → 3

Reversing a foundation transfer depends on whether
the trial period (§4.7) is in effect.

- **During the trial period.** Reversal is
  straightforward: invoke the sunset clause per
  §4.7. The TSC and founders reclaim the assets,
  the foundation is dissolved (or the project
  relationship ends), and the project returns to
  Phase 2 (or earlier) governance. The procedure
  is documented in the sunset clause itself.

- **After the trial period is formalized (sunset
  clause removed).** Reversal is not feasible in
  the same way. The foundation has full ownership
  of the assets, the sunset clause is gone, and
  reclaiming them would require the foundation's
  dissolution or a separate project to fork off.

This asymmetry is intentional. The trial period is
the project's safety valve. After the trial period
is formalized, the transition is a commitment, not
an experiment. The trial period exists precisely to
allow the project to evaluate the foundation
arrangement before making a permanent commitment.

### 5.3 Lessons from a reversal

If a phase transition is reversed, a post-mortem is
published in `decisions/`. The post-mortem:

- Documents what went wrong
- Identifies what the new structure should do
  differently
- Is published publicly, so the broader open-source
  community can learn from it

Reversals are not failures; they are learning
opportunities.

## 6. Governance Evolution

### 6.1 What can be changed

QSSL's governance documents can be amended, but
with different levels of authority:

| Document | Phase 1 authority | Phase 2+ authority |
|---|---|---|
| `CHARTER.md` | Both founders (each has veto) | TSC unanimous + founder ratification |
| `GOVERNANCE.md` | Project lead + both founder representatives | TSC |
| `governance/sponsorship.md` | Both founders | Both founders (founder agreement only) |
| `governance/roles.md` | Project lead + both founder representatives | TSC |
| `governance/evolution.md` (this doc) | Project lead + both founder representatives | TSC |
| `governance/working-groups.md` | Project lead + both founder representatives | TSC |
| `governance/decision-making.md` (Phase 2) | (not yet in force) | TSC |
| `governance/conflict-resolution.md` (Phase 2) | (not yet in force) | TSC |
| `CODE_OF_CONDUCT.md` | Project lead + both founder representatives | TSC |
| `CONTRIBUTING.md` | Project lead | TSC |
| `policies/*` | Project lead | TSC |
| `standards/*` | Project lead | TSC |
| `guidelines/*` | Project lead | TSC |
| `decisions/` ADRs | Project lead | TSC chair |

The hierarchy of authority is:

1. `CHARTER.md` is the highest-authority document.
2. `GOVERNANCE.md` is next.
3. Detailed governance documents (this file, `roles.md`,
   etc.) are next.
4. Policies, standards, and guidelines are below
   detailed governance.

In the event of a conflict, the higher document
prevails, unless the higher document has been amended
to delegate authority to the lower document.

### 6.2 How governance is amended

The default procedure for amending a governance
document is:

1. **Proposal.** A contributor opens a PR to the
   relevant document. The PR description explains
   the proposed change and the rationale.
2. **Discussion.** A comment period of at least 7
   days is held. Charter amendments and Phase 3
   transitions require longer periods (14 and 30
   days, respectively).
3. **Decision.** The body with authority decides
   per the table in §6.1.
4. **Recording.** The amendment is recorded in
   the document's own decision log and in a
   `decisions/` ADR summarizing the change.

### 6.3 Compatibility across phases

Governance documents written in Phase 1 may contain
references to Phase 1 structures (e.g., "the project
lead"). In Phase 2, these references are read as
referring to the equivalent Phase 2 structure:

| Phase 1 reference | Phase 2 equivalent | Phase 3 equivalent |
|---|---|---|
| Project lead | TSC chair | TSC chair |
| Founder representative (veto) | TSC member (founder seat) | TSC member (founder seat) |
| Project lead + founder consultation | TSC decision | TSC decision |
| QSS Corp. steering committee (Phase 2 trigger) | (no longer relevant) | (no longer relevant) |
| TSC | TSC | TSC |

A formal "translation" of Phase 1 documents to
Phase 2 nomenclature is part of the Phase 1 → 2
transition (per §3.5.2). Subsequent amendments use
the new nomenclature.

## 7. Edge Cases and Contingencies

### 7.1 Founder leaves mid-transition

If a founder leaves (per `governance/sponsorship.md`
§8) between the decision to transition and the
effective date of the transition, the transition is
paused and re-evaluated. The remaining founder and
the project lead decide whether to:

- Proceed with the transition under the remaining
  founder's stewardship
- Postpone the transition until a successor steward
  is found
- Reverse the transition decision

### 7.2 No external maintainer candidates

If, when a Phase 1 → 2 transition is being prepared,
there are no eligible external maintainer candidates
(e.g., the project is still primarily founder-driven),
the transition is postponed. The project continues in
Phase 1, and the founders revisit the question
periodically (e.g., every 6 months).

### 7.3 TSC reaches deadlock

If the TSC cannot make decisions due to deadlock
(e.g., 2 founders + 1 external, with the external
disagreeing with both founders on a key question),
the deadlock is resolved per `governance/sponsorship.md`
§7 (founder-level conflict resolution) for charter-
level matters, or by a community consultation for
operational matters.

A persistent deadlock that cannot be resolved may
trigger a transition reversal (§5.1).

### 7.4 Founder disagreement about Phase 3

If the two founders cannot agree on a Phase 3
transition, the matter is handled per
`governance/sponsorship.md` §7. The status quo
(Phase 2) is preserved. The matter may be revisited
later.

### 7.5 A founder ceases to exist

If a founding organization is dissolved, acquired,
or otherwise ceases to exist as a separate entity,
the corresponding founder representative role is
vacated. Per `governance/sponsorship.md` §8, the
project continues under the remaining founder (or
under a successor steward, if one has been
designated). This may trigger a Phase 3 transition
to ensure legal and financial continuity.

## 8. Cross-References

- `CHARTER.md` §5.3 — the three-phase policy
- `GOVERNANCE.md` §2 — governance bodies per phase
- `GOVERNANCE.md` §9 — high-level phase transition
  procedures
- `governance/sponsorship.md` — founder relationship,
  withdrawal, dissolution
- `governance/roles.md` — role definitions (TSC
  members, founder representatives, etc.)
- `governance/working-groups.md` — working group
  rules
- `decisions/` — Architecture Decision Records

## 9. Decision Log

| Version | Date | Summary | Authority |
|---|---|---|---|
| 1.0 | 2026-08-08 | Initial evolution document. Defines detailed procedures for the Phase 1 → 2 transition (trigger, preparation, TSC formation via maintainer election, first TSC actions, post-transition review), the Phase 2 → 3 transition (fiscal host selection, asset transfer, dedicated foundation setup if applicable, post-transition governance, **trial period with sunset clause as the recommended path for any first-time foundation transition**), reversal procedures for Phase 1 → 2 and Phase 2 → 3 (the latter is reversible during the trial period; afterwards it is a commitment), governance amendment procedures, compatibility across phases, and edge-case handling. | Project lead |

---

*This document is the operational procedure for QSSL's
governance evolution. It is expected to be amended as the
project grows. The most reliable statement of any
transition procedure is always the latest version of this
file in the repository.*
