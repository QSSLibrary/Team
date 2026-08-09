# QSSL Working Groups

> Rules for forming, operating, leading, and dissolving
> working groups within the QSSL project. Working groups
> are self-organizing teams around focused scientific or
> technical areas. They can be established in any phase,
> including Phase 1.
>
> **Status:** Active
> **Version:** 1.0
> **Effective date:** 2026-08-08
> **Supersedes:** none
> **Amends:** none
> **Authoritative copy:** this file at
> `governance/working-groups.md` in the `QSSLibrary/Team`
> repository

---

## 1. Purpose and Scope

This document defines how working groups (WGs) work in
QSSL. It covers:

- What a working group is and is not
- How a working group is formed
- How a working group operates day-to-day
- How a working group's scope is defined and policed
- How a working group's lead is selected
- How a working group is dissolved
- How working groups relate to project governance

The high-level summary is in `GOVERNANCE.md` §7. This
document is the operational detail.

In the event of a conflict between this document and
`GOVERNANCE.md` or `CHARTER.md`, those documents prevail.

## 2. What a Working Group Is

A working group is a **self-organizing team of
contributors** focused on a specific scientific or
technical area within QSSL's scope. Examples:

- Cosmology
- Celestial mechanics
- Coordinate systems and time scales
- Spectroscopy
- Imaging
- Core infrastructure (build, CI, tooling)
- Documentation
- Bindings (when applicable)

Each working group has:

- A **name** (short, descriptive)
- A **scope** (the area it owns; see §6)
- A **lead** (the coordinator; see §7)
- A **Discord channel and role** (for synchronous
  communication)
- A **GitHub team** (for permissions and mentions)
- A subset of issues, PRs, and discussions within its
  scope

## 3. What a Working Group Is Not

A working group is **not**:

- A separate project with its own governance, code of
  conduct, or release authority
- A way to bypass QSSL's overall governance
- A team with a separate budget or funding
- A team that can speak on behalf of QSSL in external
  contexts
- A team with authority to expand its own scope
  unilaterally
- A team with authority to make decisions binding on
  the project outside its scope

A working group that wants to do any of the above
must escalate to the project lead (Phase 1) or TSC
(Phase 2+).

## 4. Why Working Groups Exist

Working groups exist to:

- **Distribute ownership.** Different areas of the
  project have different experts and different
  communities. Working groups give each area a
  natural home.
- **Onboard new contributors.** New contributors can
  join a working group and contribute within a
  well-defined area, without needing to understand
  the whole project.
- **Enable focused collaboration.** Smaller groups
  with shared context can move faster than a single
  large project.
- **Preserve context.** Each working group
  accumulates domain knowledge that doesn't have to
  live entirely in any one person's head.
- **Reduce bottleneck on the project lead.** Most
  decisions can be made within a working group; the
  project lead or TSC only gets involved in
  cross-cutting or out-of-scope questions.

Working groups are not a bureaucratic layer. They are
a structural recognition of how scientific and
engineering work actually happens: in focused teams
with shared context.

## 5. Forming a Working Group

### 5.1 Who can propose a working group

Anyone can propose a working group. A working group
proposal is typically submitted by:

- A contributor who sees unmet need in a specific area
- A maintainer who wants to formalize informal
  collaboration
- The project lead (Phase 1) or TSC (Phase 2+), as a
  strategic decision

### 5.2 The proposal

A working group proposal is a brief document (a PR
to `Team/proposals/`, a GitHub Discussion, or a
Discord post) that includes:

- **Name.** A short, descriptive name (e.g.,
  "Cosmology WG", "Imaging WG").
- **Scope.** What the WG will and will not do. The
  scope should be specific enough to be actionable
  but broad enough to allow meaningful work.
- **Initial lead.** Who will coordinate the WG.
- **Initial membership.** Anyone who has expressed
  interest in joining (this can be 0 — the WG may
  form to attract its first members).
- **Rationale.** Why this WG should exist. What
  work is currently unowned or under-owned that the
  WG will take on?
- **Overlap analysis.** If the proposed WG
  overlaps with an existing WG, how will the
  boundaries be managed? For parent/sub proposals,
  see §6.2.
- **Type.** Whether this is a "leaf" WG (no
  sub-WGs expected), a "parent" WG (will likely
  have sub-WGs), or a "sub" WG (operating under an
  existing parent).

A reusable proposal template is in
`templates/proposal.md`. Proposals that follow the
template are easier to review.

### 5.3 Approval

A working group is formed when the proposal is
approved by the project lead (Phase 1) or TSC
(Phase 2+).

The approval process is:

1. **Proposal submitted** (per §5.2)
2. **Public comment period** of 7–14 days
3. **Decision** by the project lead or TSC, with
   reasons documented
4. **Recorded** in a `decisions/` ADR
5. **Infrastructure set up** (Discord channel, role,
   GitHub team) — typically within 7 days of
   approval

The project lead or TSC may:

- Approve the WG as proposed
- Approve with modifications (e.g., narrower scope)
- Defer (e.g., if the proposal needs more work)
- Reject (with reasons)

There is **no appeal** from a rejection, but a
revised proposal may be submitted.

### 5.4 The first 90 days

A newly formed WG has 90 days to demonstrate that
it is operational — that is, that it has:

- A lead (per §7)
- At least 2 members (including the lead)
- Made some progress on its scope (issues triaged,
  discussions started, or work begun)

**Tracking the 90-day window.** The 90-day
operational check is tracked in a **GitHub Project**
on the `QSSLibrary` organization (see
`GITHUB-PROJECTS-PLAN.md` in this repository's
working notes for the setup plan). The project
board:

- Has a "WG Operational Check" view that lists
  every WG with its formation date
- Sends an automated reminder at 80 days (10-day
  warning) and at 90 days (check due)
- Tracks the operational criteria above per WG
- Becomes the source of truth for the project's
  working-group health

**If the WG is not operational after 90 days,** the
project lead or TSC may:

- Extend the runway (if the WG shows progress
  despite not meeting the bar)
- Pause the WG (if it needs restructuring)
- Dissolve the WG (if it has not gained traction)

**Continuing activity monitoring.** After the
initial 90-day check, working-group activity is
monitored on the same GitHub Project. The
inactivity-dissolution trigger in §10 is
implemented as an automated check based on the
project board's last-activity date.

## 6. Working Group Scope

### 6.1 Scope discipline

A working group's scope is the area it owns. The
scope is defined at formation and recorded in the
WG's founding ADR. The scope is **exclusive** in
the sense that:

- Issues and PRs within a WG's scope are routed to
  that WG's triage and review
- WGs do not work outside their scope without
  coordination with the relevant WG or escalation
  to the project lead/TSC

### 6.2 Scope overlap and parent / sub WGs

When a piece of work falls in two or more WGs'
scopes, the leads and members of the affected WGs
collaborate to make a **joint decision**. The
collaboration is by default, not by exception.

**Joint decision process:**

1. **Each affected WG lead** is informed of the
   cross-WG work.
2. **A joint working session** (Discord call or
   thread) is held, attended by the leads and
   interested members of each affected WG.
3. **A joint proposal** is drafted, listing the
   shared scope, the agreed approach, and the
   contributions of each WG.
4. **Each WG's lazy-consensus process** (§8.2) is
   run on the joint proposal. The proposal is
   accepted if every affected WG accepts it
   (no objections in any WG's consensus window).
5. **Implementation** is split per the proposal,
   with cross-WG code review.

If the WGs cannot reach joint consensus (e.g., a
WG objects), the matter escalates to the project
lead (Phase 1) or TSC (Phase 2+).

**Example:** Building QSSL's
`SphericalAstronomy` submodule requires the
collaboration of the Celestial Sphere WG and the
Spherical Trigonometry WG. The joint decision
might allocate the celestial-coordinate primitives
to the Celestial Sphere WG, the spherical-trig
primitives to the Spherical Trigonometry WG, and
the integration tests to a joint effort.

**Parent / sub WG hierarchy.** QSSL supports a
hierarchy of working groups:

- A **parent WG** owns a broad scope (e.g.,
  "Astronomy" or "Infrastructure").
- A **sub WG** is established by its parent to
  handle a more focused sub-scope (e.g.,
  "Spherical Astronomy" under "Astronomy", or
  "Build System" under "Infrastructure").
- Sub WGs **inherit** the parent's governance,
  have narrower scope, and report up to the
  parent.
- A parent WG's lead is typically a project lead
  or TSC member (Phase 2+) by designation, to
  ensure accountability for the broad scope.
- A sub WG's lead is appointed by the parent
  lead with input from the parent WG's members.
- The parent WG may define specific
  sub-scope-spanning tasks that sub WGs
  coordinate on (this is one valid use of the
  parent/sub relationship).

**Why parent / sub.** The hierarchy supports
collaborative work on complex features that span
multiple scientific or technical areas, without
forcing a flat structure to handle every
overlap case. The hierarchy is **not** a
management chain — it does not give parent WGs
authority to command sub WGs. It is a **scope
and accountability** structure.

**Discipline:** the parent/sub relationship is
used to organize genuinely hierarchical work, not
to create artificial layers. A flat structure (no
parent/sub) is the default; the hierarchy is
introduced only when it provides real
organizational value.

### 6.3 Scope changes

A WG's scope is not fixed. It may be:

- **Narrowed.** A WG may decide that part of its
  scope belongs elsewhere. This requires project
  lead or TSC approval.
- **Broadened.** A WG may take on new scope if no
  other WG owns it. This requires project lead or
  TSC approval and a public comment period.
- **Split.** A WG may split into two or more WGs
  if its scope has grown too broad. This is a
  formation event (per §5) for the new WGs and a
  dissolution event (per §10) for the old one.

### 6.4 Out-of-scope work

A WG that wants to do work **outside its scope**
(e.g., the Imaging WG wanting to add a game engine
tutorial) must either:

- Request a scope change (per §6.3), or
- Coordinate with the relevant WG, or
- Escalate to the project lead or TSC

A WG that does out-of-scope work without
authorization is acting outside its mandate. The
project lead or TSC may ask the WG to stop, reverse
the work, or formalize the scope change.

## 7. Working Group Leads

### 7.1 Role

The working group lead is the coordinator of the WG.
They are not the "boss" of the WG members; they are
the person who:

- Sets the WG's short-term priorities within its
  scope
- Coordinates meetings and discussions
- Reports to the project lead (Phase 1) or TSC
  (Phase 2+)
- Onboards new members
- Surfaces scope disputes and cross-cutting issues

The lead is a coordinator, not a gatekeeper. They
do not have authority to make decisions binding on
the WG; decisions are made by the WG members
collectively (typically by lazy consensus — see
§8.2).

**Internal team management.** Each working group
has its own **GitHub Discussions** area on the
relevant repository (or on the `Team` repository
for project-wide WGs) where the WG manages its:

- Internal discussions
- Meeting notes and minutes
- Decision records
- Onboarding documentation for new members
- Working drafts and design documents

The WG's GitHub Discussions space is the WG's
durable record. Discord is for synchronous chat;
GitHub Discussions is for the things that need
to be findable later. The WG lead is responsible
for ensuring that important decisions and notes
make it into Discussions, not just Discord.

### 7.2 Selection

The initial lead is proposed in the WG's formation
proposal (§5.2) and confirmed by the project lead
or TSC. Subsequent leads are selected by one of:

- **Self-selection.** An existing member volunteers
  and is accepted by the other members (lazy
  consensus).
- **Election.** If there are multiple candidates or
  if the WG prefers a formal process, a vote is
  held among WG members.
- **Appointment by project lead or TSC.** Used as a
  last resort if the WG cannot self-organize a
  selection.

### 7.3 Term

There is no fixed term. A lead serves at the
pleasure of the WG members. The lead may step down
at any time, with notice to the project lead or
TSC and to the WG.

### 7.4 Removal

A WG lead may be removed by:

- **The WG members.** A vote of no confidence by ⅔
  of active WG members. The removal is **confirmed
  by the project lead (Phase 1) or TSC (Phase 2+)**
  — the project lead or TSC holds a veto on the
  removal. This veto is intended to protect against
  factional or retaliatory removals and to ensure
  that the removal is consistent with the project's
  governance.
- **The project lead or TSC.** For sustained
  inactivity, CoC violations, or conduct that
  materially harms the project. This is independent
  of any WG member vote.

If the project lead or TSC vetoes a member-initiated
removal, the project lead or TSC issues a public
explanation. The WG may then escalate per the
dispute-resolution procedures in `GOVERNANCE.md` §5.

### 7.5 Multiple leads (or no lead)

A WG may have any number of co-leads, including
zero. The number of co-leads is a function of the
WG's nature:

- **Leaf WGs** (focused, narrow scope) may have a
  single lead, or occasionally two co-leads.
- **Parent WGs** (broad scope, sub-WGs underneath)
  often benefit from multiple co-leads representing
  different sub-areas, to ensure coverage of the
  broad scope.
- **Low-level or task-specific sub-WGs** may
  temporarily operate without a formal lead, with
  the parent WG's lead acting as coordinator until
  a sub-WG lead is identified.
- **A WG with no co-leads and no parent-lead
  coordinator** is a dormant WG and is subject to
  the inactivity procedures in §10.

Co-leadership is healthy when the co-leads have
clearly divided responsibilities; it is unhealthy
when it creates ambiguity about who is in charge.
The WG's ADR (per §7.2) records the chosen
co-leadership structure and the division of
responsibilities.

### 7.6 Lead authority

The lead does **not** have authority to:

- Speak on behalf of QSSL in external contexts
- Make decisions binding on QSSL beyond the WG
- Modify the WG's scope (per §6.3)
- Remove WG members (members leave on their own
  initiative; removal is rare and a CoC matter)
- Hire or pay people (WGs do not have budgets)
- Accept funding on behalf of QSSL
- Sign legal agreements on behalf of QSSL

The lead **does** have authority to:

- Set the WG's short-term priorities within scope
- Schedule and run WG meetings
- Triage issues and PRs in the WG's scope
- Recommend contributors for maintainer status
  (for the WG's area)
- Represent the WG in cross-WG discussions
- Make public statements about the WG's work (in
  their role as lead)

**Future funding and recognition mechanisms.**
The current governance does not provide budgets or
financial support for WGs. However, the design
anticipates that future mechanisms may be
established, including:

- **Project lead or TSC-led contests and
  recognition.** The project lead (Phase 1) or TSC
  (Phase 2+) may establish contests, awards, or
  other recognition programs to celebrate WGs that
  reach significant milestones.
- **Sponsorship of WGs by Cuby Inc. or QSS
  Corp.** As founding sponsors, Cuby Inc. and QSS
  Corp. may, at their discretion and subject to
  sponsor neutrality (per `CHARTER.md` §5.2),
  provide financial or in-kind support to WGs that
  reach their expectations. Such support is
  recorded in a `decisions/` ADR and is
  transparent.
- **Grant-funded WGs.** In Phase 3 (foundation
  hosted), WGs may receive grant funding through
  the foundation. The terms of any such funding
  are documented per WG.

These mechanisms are **not yet active**; they are
described here so the governance accommodates them
when they are introduced. The lead's authority does
not change until a specific mechanism is formally
adopted.

## 8. Working Group Operations

### 8.1 Communication

- **Synchronous:** Discord channel dedicated to the
  WG. The channel is the WG's primary real-time
  communication space.
- **Asynchronous:** GitHub issues, PRs, and
  discussions in the relevant repositories, tagged
  with the WG's label (e.g., `wg-cosmology`).
- **Cross-WG:** A common Discord category
  (`working-groups`) and GitHub team for general
  cross-WG discussion.

### 8.2 Decision-making

WGs make decisions by **lazy consensus**: a
proposal is accepted if no WG member objects
within a reasonable time (typically **3 days**,
or less for urgent matters). Lazy consensus is the
default because it is fast and works well in
focused groups.

If a decision cannot be reached by lazy consensus
(e.g., a strong objection), the lead may:

- Facilitate a discussion to find a compromise
- Call a vote (simple majority of active WG
  members)
- Escalate to the project lead or TSC

### 8.3 Tracking work

Each WG uses GitHub issues and PRs in the relevant
QSSL repositories to track its work. The WG may
choose additional tools (project boards, design
docs) as needed, but GitHub is the source of truth
for code-related work.

### 8.4 Releases

WGs do not have their own release authority.
Releases are made by the project lead (Phase 1) or
TSC (Phase 2+). A WG's work is included in a QSSL
release when the project lead or TSC decides to
include it.

A WG's lead may propose a release containing the
WG's work, but the project lead or TSC has the
final say.

## 9. Working Group Members

### 9.1 Joining

A working group is open to any contributor.
Joining is by:

- **Self-selection:** expressing interest in the
  WG's Discord channel, GitHub team, or in a
  relevant issue/PR
- **WG lead acceptance:** the lead may accept or
  decline new members based on the WG's capacity

There is no formal application or vetting process.
A new member is expected to:

- Read the WG's scope and any orientation docs
- Introduce themselves in the WG's channel
- Find an initial piece of work (or ask the lead
  for suggestions)

### 9.2 Participating

A WG member is expected to:

- Participate in the WG's discussions
- Follow the WG's coordination conventions
- Uphold the code of conduct
- Do useful work in the WG's scope (the definition
  of "useful" is intentionally loose — even
  small contributions count)

There is no minimum activity level. A WG member
may participate as their time and interest allow.

### 9.3 Authority

A WG member has authority to:

- Submit PRs and issues in the WG's scope
- Participate in WG decisions
- Vote in WG votes (per §8.2)
- Leave the WG at any time
- Belong to **multiple WGs simultaneously**, or to
  no WG at all. WG membership is not exclusive.

A WG member does **not** have:

- Maintainer privileges (unless separately appointed)
- Authority to make decisions on behalf of QSSL
  beyond the WG
- Authority to speak on behalf of QSSL

**Important: contributors can always submit PRs and
issues to any QSSL repository**, regardless of WG
membership. WG membership is not a gate to
contribution. A contributor who is not a member of
any WG is a perfectly normal state, and the
contributor is welcome to submit PRs, file issues,
and participate in discussions across the project.
The WG structure is for **coordination**, not for
**access control**.

### 9.4 Leaving

A WG member may leave at any time, with or without
notice. The lead may ask a member to leave if the
member's behavior is disruptive, but this is
unusual and a CoC matter if serious.

A member who has been inactive for 6+ months may
be removed from the WG's GitHub team and Discord
role. This is an administrative cleanup, not a
punishment; the member can rejoin at any time.

## 10. Dissolving a Working Group

A working group is dissolved when:

- The WG has been inactive for 6+ months (no
  significant activity in the WG's scope, no
  meetings, no member engagement)
- The WG's scope has been fully absorbed by other
  WGs
- The WG's lead and a majority of members request
  dissolution
- The project lead or TSC determines that the WG
  is not serving the project

### 10.1 Procedure

1. **Initiation.** Dissolution is initiated by:
   - The lead, with majority support of members
   - A petition of ⅔ of members
   - The project lead or TSC
2. **Public comment period** of 14 days.
3. **Decision** by the project lead or TSC.
4. **Recorded** in a `decisions/` ADR.
5. **Infrastructure cleanup** — Discord channel
   archived, GitHub team archived, work transferred
   to successor WGs (if any).

### 10.2 Disposition of work

When a WG is dissolved, its in-progress work is
transferred:

- To another WG that owns the relevant scope
- To the project lead or TSC (if no successor WG)
- To individual maintainers willing to take it on

The disposition of work is recorded in the
dissolution ADR.

**Call for new teams or individuals.** When a WG
is dissolved and its scope is not absorbed by
another WG, the project lead or TSC announces the
opening in:

- The QSSL Discord server (in the relevant channel
  and in a server-wide announcement)
- The `Team` repository's GitHub Discussions
- The QSSL GitHub Project (per §5.4) so the call
  for new teams is tracked alongside WG health

The call invites new teams or individuals to pick
up the scope. The call remains open for at least
30 days before the scope is considered
unclaimed, at which point the project lead or TSC
decides whether to:

- Re-form the WG under new leadership
- Leave the scope dormant (with the understanding
  that no one is currently responsible for it)
- Reassign the scope to another existing WG

## 11. Research Groups (RGs) — Coordination with IRC-ATL

QSSL's working groups are **development-focused**:
they build and maintain the library. QSSL also
benefits from **research groups (RGs)**, which are
**research-focused**: they use QSSL (and contribute
back to it) to do original scientific work.

### 11.1 Where RGs live

RGs are coordinated through a separate GitHub
repository: **`QSSL-Research-Teams`**, hosted in the
**IRC-ATL** GitHub organization
(International Research Center: Ālenush Teriān Lab
(ATL); description: *"Advancing astrophysics
through computational science, AI, and open
research. Home to code, data, and discoveries from
the Ālenush Teriān Lab (ATL)"*).

**About IRC-ATL.** IRC-ATL is a research
laboratory within the **IRC Research Laboratory**,
an international research group initially founded
by QSS Corp. IRC-ATL is not a company; it is a
research organization with members distributed
across institutions and countries. The principal
of IRC-ATL is also the QSSL project lead (Ramtin
Kosari), but the two organizations have distinct
governance, distinct missions, and (over time)
distinct leadership. WGs (in QSSL) and RGs (in
IRC-ATL) are coordinated, but each is governed by
its own organization.

This separation is intentional:

- WGs (in QSSL) handle **library development**.
- RGs (in IRC-ATL) handle **research using the
  library**.
- The two have different lifecycles, different
  governance, and different success metrics.
- Library development and research are related but
  distinct activities; conflating them creates
  governance confusion.

### 11.2 RG-to-WG feedback

RGs produce a wide range of outputs that can
benefit QSSL, including but not limited to:

- **Missing primitives.** A research project
  reveals a function or class that QSSL should
  have but doesn't.
- **New algorithms.** A research project develops
  a new algorithm (e.g., a faster or more
  numerically stable method) that could be added
  to QSSL.
- **Optimizations.** A research project's profiling
  work reveals a performance issue that a QSSL
  optimization could address.
- **Correctness fixes.** A research project's
  validation work reveals a bug, an off-by-one
  error, or a sign error in QSSL.
- **Reference data and validation.** A research
  project produces reference data, benchmark
  results, or validation studies that improve
  QSSL's test suite and documentation.
- **Documentation improvements.** A research
  project produces clearer explanations of
  scientific concepts that can improve QSSL's
  documentation.
- **Test cases.** A research project's edge cases
  become new test cases for QSSL.

All of these flow back to the relevant WG via the
standard contribution process:

- An RG member opens an issue or PR in the
  relevant QSSL repository
- The relevant WG triages and reviews it
- The RG member follows the standard `CONTRIBUTING.md`
  process (DCO, code review, etc.)

RGs do **not** merge directly into QSSL
repositories. Library changes flow through the WG
process, not the RG process.

### 11.3 WG-to-RG seeding

A WG that identifies a research opportunity (e.g.,
a missing empirical validation, a need for
benchmark data, an interesting theoretical case
study) may propose the formation of an RG to
address it. The proposal is communicated to
IRC-ATL through standard channels (GitHub issue
in the `QSSL-Research-Teams` repo, Discord
cross-post, or direct communication between the
project lead and IRC-ATL leadership).

WGs do **not** create RGs directly. RGs are
created by IRC-ATL under IRC-ATL governance.

### 11.4 Why this split

The IRC-ATL-hosted RG model:

- Lets research be organized by the research
  community (under IRC-ATL's research-oriented
  governance) rather than by the library's
  development governance
- Allows RGs to publish papers, host datasets, and
  do other research activities that don't fit
  cleanly into a library-development WG
- Preserves QSSL's focus on the library itself
- Enables IRC-ATL to grow its research community
  independently of the library
- Creates a healthy feedback loop: research
  improvements flow into the library; library
  improvements enable new research

The detailed RG governance (formation, scope,
funding, publication policy) lives in the
`QSSL-Research-Teams` repository under IRC-ATL.
This document only covers the **relationship
between WGs and RGs**.

## 12. Cross-References

- `CHARTER.md` §3.2 — out-of-scope (WGs operate
  within the project's domain)
- `GOVERNANCE.md` §7 — high-level WG summary
- `governance/roles.md` — role definitions,
  including WG leads and members
- `governance/sponsorship.md` — for the case where
  a WG involves a founder's other projects
- `CODE_OF_CONDUCT.md` — applies to all WG
  interactions
- `IRC-ATL/QSSL-Research-Teams` (separate
  repository) — Research Group governance and
  coordination
- `templates/proposal.md` — reusable proposal
  template for new WGs
- `GITHUB-PROJECTS-PLAN.md` (working notes, not
  for commit) — GitHub Projects setup plan for
  WG activity tracking

## 13. Decision Log

| Version | Date | Summary | Authority |
|---|---|---|---|
| 1.0 | 2026-08-08 | Initial working-groups document. Defines WGs as self-organizing teams within QSSL's governance, with formation (§5; with GitHub Projects tracking of the 90-day operational check and ongoing activity monitoring), scope discipline (§6; with joint decision-making for cross-WG work and a parent/sub WG hierarchy for genuinely hierarchical work), leads (§7; with GitHub Discussions for internal team management, project lead/TSC veto on member-initiated removals, flexible co-leadership, and a noted future funding/recognition mechanism), operations (§8; with 3-day lazy consensus), membership (§9; with multi-WG/no-WG contributor rights, and 6-month inactivity cleanup), dissolution (§10; with Discord/Discussions/Project call for new teams), and Research Group coordination (§11; with IRC-ATL as the home for research teams, separate from development WGs). | Project lead |

---

*This document is the operational rulebook for QSSL
working groups. It is expected to be amended as the
project's working-group structure evolves. The most
reliable statement of any working-group rule is always
the latest version of this file in the repository.*
