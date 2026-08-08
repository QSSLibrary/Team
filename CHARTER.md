# QSSL Project Charter

> The foundational document of the QSSL project. Defines mission, scope,
> non-goals, governance philosophy, founding stewardship, and the path
> to independence. Read this first; everything else is implementation.
>
> **Status:** Active
> **Version:** 1.0
> **Effective date:** 2026-08-08
> **Supersedes:** none
> **Amends:** none
> **Authoritative copy:** this file at the root of the
> `QSSLibrary/Team` repository

---

## 1. Mission

QSSL (QSS Library) is an open-source C++ library that provides
rigorous, well-tested, and reusable computational primitives for
**astronomy, astrophysics, and adjacent scientific domains**. Its
purpose is to make correct astronomical and astrophysical computation
accessible to anyone who needs it — researchers, students, educators,
and developers across research, education, and applied industries —
without requiring every project to re-implement the same fundamental
algorithms.

QSSL is built and maintained by a community of contributors under the
stewardship of its founding organizations. The library is independent
of any single entity, company, or institution. It exists for the
public good of computational science.

## 2. Vision

QSSL aspires to become a **foundational layer** for computational
astronomy and astrophysics in C++: a library that is the natural
starting point for new projects in the domain, that other libraries
build on, and that is trusted by working scientists.

The long-term goal is not to replicate what already exists in other
ecosystems (e.g., astropy in Python), but to provide a
comparable-quality, native, performant option for C++ users and for
projects where C++ is the natural choice — including performance-
sensitive simulations, embedded systems, game and simulation
engines, and engineering applications.

## 3. Scope

### 3.1 In scope

Computational primitives, algorithms, and reference data for:

- **Astronomy** — positional astronomy, time keeping, calendars,
  reference catalogs
- **Astrophysics** — stellar, galactic, and extragalactic physics
- **Celestial mechanics** — orbital dynamics, n-body, perturbation
  theory, ephemerides
- **Cosmology** — cosmological models, distance measures, large-
  scale structure
- **Spectroscopy** — astronomical spectra, line lists, Doppler
  shifts, redshift
- **Spherical astronomy** — coordinate transformations, precession,
  nutation, aberration, refraction
- **Coordinate systems and reference frames** — ICRS, galactic,
  ecliptic, equatorial, topocentric, body-fixed, etc.
- **Time scales and time conversions** — UTC, TAI, TT, TDB, TCB,
  Julian Date, Modified Julian Date, sidereal time
- **Units and unit conversions** — SI, cgs, astronomical units
  (AU, parsec, light-year, solar mass/luminosity/radius, etc.)
- **Imaging of astronomical data** — FITS I/O, image calibration,
  photometry, basic reduction
- **Numerical methods** specific to the above (root-finding,
  integration, interpolation, statistical methods used in astro)

### 3.2 Out of scope (non-goals)

QSSL is **explicitly not** the following:

- A replacement for astropy, or any other Python astronomy stack.
  (QSSL serves a different ecosystem.)
- A general-purpose scientific computing library. For linear
  algebra, optimization, or generic numerics, use Eigen,
  BLAS/LAPACK, or similar.
- A non-astronomical physics domain library. Topics such as
  condensed matter, pure particle physics, fluid dynamics
  unrelated to astrophysics, and quantum chemistry are out of
  scope. (QSSL is *for* astronomy and astrophysics; it does not
  *implement* every other branch of physics.)
- A build system, package manager, or CI/CD platform.

### 3.2.1 Important clarification: scope vs. use cases

Several items that might appear in an "out of scope" list are
deliberately **not** included, because they are *uses* of QSSL
rather than features QSSL itself would implement. These are
**welcomed use cases**, not exclusions:

- **Game engines and game frameworks.** QSSL provides orbital
  mechanics, time, and coordinate primitives that game engines
  use as a foundation. Cuby Inc.'s **Synestia-Studio** game
  studio, for example, is building space-themed games and a
  space-game engine on top of QSSL. The library does not need
  to *be* a game engine to be useful to one.
- **GUI toolkits, web front-ends, and visualization software.**
  QSSL provides the data and primitives; GUI front-ends are
  separate applications that consume them. QSS Corp.'s
  **IRC-ATL** research group, for example, plans to develop
  amateur-astronomer software with graphical interfaces on top
  of QSSL.
- **Telescope control systems and instrument drivers.** QSSL
  provides the computational layer; hardware control is a
  separate concern. A telescope control system that uses QSSL
  for coordinate transformations, sidereal time, and pointing
  calculations is a *user* of QSSL, not an out-of-scope
  extension.
- **Embedded and aerospace systems.** QSSL's permissive
  license and C++ foundation make it appropriate for embedded
  and aerospace use (rockets, satellites, control systems).
  These are users; they do not change the library's domain.
- **AI, machine learning, and deep learning applications.**
  Pre-processing, feature extraction, and ML pipelines that
  operate on astronomical data are welcome users. QSSL does
  not need to *be* an ML library to be useful in ML pipelines.
- **Language bindings for other languages** (Python, Rust,
  etc.) are out of scope *for the QSSL project itself* but
  may be developed as separate community projects. The QSSL
  project maintains C++ first; bindings, if any, are
  community-driven once the C++ API is stable.

The principle: **QSSL's scope is the library itself. What
people build on top of it, or wrap around it, is up to them.**

### 3.3 The scope-vs-users distinction

The library's **scope** is astronomy and astrophysics. The library's
**users** may be diverse and are explicitly welcomed:

| User category | Example use |
|---|---|
| Research astronomers and astrophysicists | Pipeline development, data analysis |
| Students and educators | Coursework, tutorials, teaching tools |
| Game and simulation developers | Orbital mechanics, procedural starfields, space games |
| Space-game studios (e.g., Cuby Inc.'s **Synestia-Studio**) | Space-themed games, space-game engines |
| Embedded and aerospace engineers | Rocket guidance, satellite operations, control systems |
| Stellarium and planetarium developers | Real-time sky rendering, position computation |
| Telescope control and observatory software | Coordinate transformations, pointing, sidereal time |
| Amateur-astronomer software developers (e.g., QSS Corp.'s **IRC-ATL** research group) | GUI tools, observation planning, education |
| Data scientists and AI/ML/DL practitioners | Pre-processing, feature engineering, ML pipelines |
| Amateur astronomers | Personal tools, observation planning |
| Commercial astronomy software vendors | Building differentiated products |
| Other scientific libraries | Building on QSSL primitives |

These are *users* of QSSL, not requests to expand its scope. A PR
that adds a general-purpose game engine because a user happens to be
a game developer is out of scope. The charter's scope is the
boundary; the user list is the welcome mat.

## 4. Governance Philosophy

QSSL is governed by the following principles:

- **Stewardship, not ownership.** No company, individual, or
  institution owns QSSL. The project exists independently of its
  founders and contributors.
- **Domain focus over feature breadth.** It is better to do a small
  number of things rigorously than to do many things poorly.
- **Open by default.** Discussions, proposals, and decisions happen
  in public channels (GitHub Issues, GitHub Discussions, Discord).
  Private DMs are not where decisions are made.
- **Documented decisions.** Material decisions are recorded in
  Architecture Decision Records (ADRs) in the `decisions/` folder
  of this repository, so that institutional memory survives
  contributor turnover.
- **Professional without bureaucratic.** Rules exist to solve
  real problems. If a rule has no problem, it should not exist.
- **Founder-led now, community-led later.** Initial governance is
  provided by the founding stewards. The long-term goal is a
  governance model independent of any single entity.
- **Continuity planned for.** Maintainer succession, contributor
  pipelines, and foundation transition are designed in, not
  bolted on after a crisis.

## 5. Founding Stewards

QSSL is founded and initially stewarded by two organizations acting
as **founding sponsors** of the project. They hold no ownership
interest in QSSL itself; their role is to provide initial
governance, infrastructure, and contributions.

| | Cuby Inc. | QSS Corp. |
|---|---|---|
| Type | Technology company | Space exploration company |
| Domain role | Engineering practices, code quality, tooling | Scientific correctness, domain authority, use cases |
| Authority type | Technical authority | Domain authority |
| Governance seat | One founder representative | One founder representative |
| Contribution mode | DCO with corporate-authorization clause | DCO with corporate-authorization clause |

### 5.1 Other projects of the founding stewards

The founding stewards have other projects and business activities
outside QSSL, including Cuby Inc.'s **Synestia-Studio** game
studio and QSS Corp.'s **IRC-ATL** amateur-astronomy research
group. These projects are **users of QSSL**, not parts of
QSSL's governance. Their existence strengthens the founders'
stake in the project — they are not only stewards in the
abstract, but also practitioners with direct interest in the
library's quality. They are not, however, channels through
which either company can direct QSSL's technical decisions.

### 5.2 Division of responsibility

The two founding stewards are **complementary, not redundant**:

- **QSS Corp.** speaks with authority on what the library should
  *do* — which scientific domains, which algorithms, which
  conventions (e.g., IAU resolutions, SOFA/ERFA reference
  implementations, coordinate system choices).
- **Cuby Inc.** speaks with authority on how the library should
  *be built* — code quality, API design, performance
  characteristics, build system, testing practices, CI/CD.

Where domain and engineering considerations conflict, the
principle is: **scientific correctness is non-negotiable; engineering
choices are negotiable.**

### 5.2 Sponsor neutrality

Neither founder, nor any future sponsor, may dictate technical
direction, set project priorities unilaterally, or override
decisions made by the project's governing body (the project lead
in Phase 1, the TSC in later phases). Sponsors contribute code,
funding, domain input, and infrastructure. They do not own the
project.

### 5.3 Path to independence

QSSL's governance is designed to evolve toward increasing
independence from its founders:

- **Phase 1 (now):** Founder-led. A project lead (one of the
  founders) holds primary decision authority, with the other
  founder representative consulted on significant matters.
  Documented in `GOVERNANCE.md`.
- **Phase 2:** A **Technical Steering Committee (TSC)** is
  formed at the discretion of the **QSS Corp. steering
  committee overseeing QSSL**, when that committee determines
  that the library has reached a level of maturity, community
  engagement, and maintainer depth sufficient to be actively
  continued under a TSC/maintainer decision structure. The
  founders' criterion is *"the library can be maintained by
  the community without the founders holding primary
  control."* Phase 2 is a judgment call, not a numerical
  threshold: it happens when the project is genuinely ready,
  not when a contributor count is reached. The TSC comprises
  both founder representatives plus 1–3 external maintainers.
  Founders transition to "stewardship" rather than "control"
  roles.
- **Phase 3:** The project is transferred to an independent
  **fiscal host** (e.g., NumFOCUS, Open Source Collective, or a
  dedicated QSSL foundation) when the TSC and founding
  stewards jointly determine that the project has reached a
  level of institutional adoption, sustained funding need, or
  community demand that warrants legal and financial
  independence. As with Phase 2, this is a judgment call by
  the current governing body, not a fixed numerical trigger.
  The founders continue as sponsors, not controllers.

The exact procedure for transitioning between phases is
documented in `governance/evolution.md` and is itself
revisable. The intent of removing numerical triggers is to
prevent rigid thresholds from being gamed or held hostage, and
to ensure that transitions happen when the project is genuinely
ready, not when a number is reached.

## 6. Project Identity

| Attribute | Value |
|---|---|
| Project name | QSSL (QSS Library) |
| Pronunciation | "Q-S-S-L" |
| License | Apache License, Version 2.0 |
| Primary repository organization | `QSSLibrary` (GitHub) |
| Primary governance repository | `QSSLibrary/Team` |
| Communication — synchronous | Discord |
| Communication — asynchronous | GitHub Issues, GitHub Discussions |
| Code contribution venue | Pull Requests on `QSSLibrary/*` |
| Formal proposal venue | Pull Requests to `Team/proposals/` |
| Decision records | Merged PRs to `Team/decisions/` |
| Code of Conduct | Contributor Covenant 2.1 |

The project's name, logo, trademarks, and visual identity are
governed as follows:

#### 6.1 Logo and visual identity

The QSSL logo and any associated visual identity (color palette,
typography, iconography, derived marks) are **designed by and
owned by QSS Corp.** The library uses only the official
QSS Corp.-provided logo, or versions explicitly approved by
QSS Corp. No third party — including contributors, downstream
users, working groups, or future governing bodies — may create
alternate logos, marks, or branding for QSSL without QSS Corp.
authorization.

This policy is **not phase-dependent**: it persists unchanged
through Phase 1, Phase 2, Phase 3, and any subsequent
governance structure, including any future fiscal host or
foundation. Use of the QSSL name and logo in derived works,
documentation, packaging, or marketing must follow the
trademark policy (to be drafted in Phase 2; until then, contact
the project lead for any branding questions).

## 7. Decision Authority

A summary; details in `governance/decision-making.md` (Phase 2).

| Decision type | Authority (Phase 1) | Authority (Phase 2+) |
|---|---|---|
| Day-to-day operations | Project lead | TSC |
| Architecture changes | Project lead + founder consultation | TSC majority |
| Scientific conventions (e.g., reference frames) | QSS Corp. (domain authority) | TSC, with domain input |
| Engineering standards (e.g., C++ floor, style) | Cuby Inc. (technical authority) | TSC, with technical input |
| Adding/removing modules | Project lead | TSC |
| Breaking API changes | Project lead + founder consultation | TSC supermajority (≥⅔) |
| Releases | Project lead | TSC |
| Charter amendments | Both founders | TSC unanimous + founder ratification |
| Maintainer appointment/removal | Project lead | TSC |
| CoC enforcement | Project lead (with co-opted reviewers as needed) | TSC-enforced process |
| Project-lead succession | Both founders | TSC + founders |
| Dissolution or transfer to foundation | Both founders | TSC + founders |

Phase 1 puts significant weight on the project lead and founders
because there is no larger community to draw on yet. This is
intentional; the design ensures that the heaviest decisions remain
reviewable rather than unilateral.

## 8. The Charter Itself

### 8.1 Authority of the charter

This charter is the highest-authority document in the QSSL project.
In the event of a conflict between this charter and any other
governance document, policy, or decision, this charter prevails,
unless and until it is amended.

### 8.2 Amending the charter

- **Phase 1:** Amendments require the affirmative agreement of
  both founding stewards. Amendments are recorded as a new version
  of this file, with a changelog entry in the decision log
  (§8.3).
- **Phase 2+:** Amendments require unanimous agreement of the TSC
  plus ratification by both founding stewards, OR a TSC
  supermajority (≥¾) after a 30-day public comment period if the
  founders decline to ratify.

The charter's three-phase governance design (§5.3) is itself
amendable, but doing so is a Phase 1 / Phase 2 / Phase 3 decision
respectively and is treated as a charter-level change.

### 8.3 Versioning and decision log

Each charter version is recorded in `decisions/CHANGELOG.md` with:

- Version number
- Effective date
- Summary of changes
- Authority that approved the change

The current charter (v1.0) is recorded below.

#### Decision log

| Version | Date | Summary | Authority |
|---|---|---|---|
| 1.0 | 2026-08-08 | Initial charter. Defines mission, scope, non-goals, governance philosophy, founding stewardship (Cuby Inc. and QSS Corp.), and the three-phase path to independence. | Both founding stewards |

## 9. Cross-References

This charter is supported by the following documents, which are
authoritative within their scope:

- `GOVERNANCE.md` — operational governance, roles, decision-making
- `governance/sponsorship.md` — Cuby Inc. ↔ QSS Corp. founding
  agreement
- `governance/roles.md` — role definitions
- `governance/evolution.md` — how governance evolves
- `CODE_OF_CONDUCT.md` — community standards and enforcement
- `CONTRIBUTING.md` — how to contribute
- `policies/licensing-and-cla.md` — DCO and corporate-contributions
  policy
- `SECURITY.md` — vulnerability disclosure
- `ARCHITECTURE.md` — *internal working document*, not authoritative
  for governance but useful as a design rationale reference

Phase 2 will add standards, policies, and templates referenced by
this charter.

## 10. Closing

This charter is a living document. It is expected to be amended as
QSSL grows, as new stewards join, and as the community's needs
evolve. Its current text reflects the project's understanding at
the effective date above. The most reliable statement of the
project's identity and governance is always the latest version of
this file in the repository.

— *The founding stewards of QSSL: Cuby Inc. and QSS Corp.*
