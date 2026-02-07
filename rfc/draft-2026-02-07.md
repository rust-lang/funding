- Feature Name: `rust_maintainer_program`
- Start Date: 2026-02-07
- RFC PR: [rust-lang/rfcs#0000](https://github.com/rust-lang/rfcs/pull/0000)

# Summary
[summary]: #summary

This RFC defines how the Rust Project collaborates with maintainer funds — organizations that provide stable funding for Rust maintainers. The Project offers three services to funds: identifying where funded maintainers would have the most impact, vetting and prioritizing applicants, and helping maintainers demonstrate their impact through the Project Goals program. In return, the Project asks funds to provide champion and reviewer bandwidth for areas the Project identifies as priorities. The RFC also describes how the Rust Foundation Maintainer Fund (RFMF) will use this interface and how maintainer funding fits into a larger system — connecting the Project Goals program's application areas and roadmaps with sponsor investment to create a coherent path from funding to shipped improvements.

# Motivation
[motivation]: #motivation

## Part 1: The maintainer side

### Rust's maintenance problem isn't backlog — it's sustained commitment

- Not just about PR queues; it's that nobody can commit to long-term work without funding
- Quote: "Nobody can commit to something for 6 months to a year where they can say now I can work on this for an entire year without knowing that they'll be funded"

### Teams are understaffed, precarious, and isolated

- Team-by-team picture: r-a went from 10 PRs to 110+ backlog when one funded person left; rustdoc has one paid contributor; Cargo is "ok but precarious"; Clippy has zero funded members; Rustup reformed after silent burnout of the entire original team
- Quote: "We are a bit low... it's slow on reviews because of that"

### Even funded maintainers often can't do maintenance

- Funding that exists tends to target features, not the enabling work that keeps Rust healthy
- Quote: "Even those funded don't necessarily get funded for maintenance... some of that is only towards features rather than things which make the whole codebase better"

### Cross-team blocking compounds the problem

- Teams block each other not from unwillingness but because nobody has the bandwidth
- Quote: "there's nobody with the expertise who is motivated to work on a problem"

### Volunteer-only maintenance is not sustainable

- The pattern: burnout → retreat → context loss → more burden on remaining people
- Quote: "Someone tends to go into burnout fairly often"
- Quote: "Years of experience can be lost in a short time when funding goes, which is why continuity is so important"

## Part 2: The sponsor side

### Companies want to invest in Rust but face structural barriers

- Three kinds of companies, each with a different relationship to Rust funding:
- **Deep investors** (Amazon, Google, Microsoft, Huawei, Ferrous Systems) — hire full-time Rust maintainers, but their compensation structures reward visible feature work, not general maintenance. Even the best-resourced teams have a maintenance gap.
- **Area investors** — depend on Rust for specific domains (networking, embedded, developer tooling) and would fund improvements, but have no path from "we have budget" to "work gets done." They don't know who to hire, what to fund, or who to talk to.
- **General supporters** — want Rust to thrive, will write a check, but need confidence the money goes where it matters.

### No path connects willing sponsors to the work that needs doing

- There's no coordination layer — no way for a company to say "I care about async Rust" and get connected to the people and teams working on it
- The result: money that exists doesn't reach the maintenance work that needs it

## Part 3: Closing the loop

### This RFC builds the path from sponsor investment to maintainer impact

- Well-funded maintainers create the capacity for teams to absorb contributions
- Sponsors — whether they want targeted investment or general support — get a clear path
- The Project Goals program, with its application areas and roadmaps, becomes the coordination layer that connects sponsor interest to Project needs
- This RFC is part of a larger system; we tell the complete story here and establish the maintainer-funding piece

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

## Design axioms

### The Project maintains its independence

- The Leadership Council decides which funds to collaborate with; this is not subject to review by the Foundation or any other entity

### Sponsors influence the when, not the what

- Sponsorship can help prioritize an area — get it attention sooner, get a maintainer to champion it
- But design decisions live with teams; sponsors are accelerating, not steering
- Sponsors may request broad areas (e.g., "async Rust") but not specific features or roadmap items

### The program supports long-term, committed maintainers

- The committee won't help select contractors for scoped jobs — that's a different relationship
- We're looking for people who will build deep context and stay

### The Project helps maintainers demonstrate their impact

- The Project provides scaffolding — Goals, program management, reporting infrastructure — so maintainers can focus on the work while sponsors get visibility into outcomes
- This is about supporting maintainers, not surveilling them

### Funds are responsible for their own operations

- Money, contracts, compensation, management, sponsor relations — all the fund's domain
- The Project does not employ, manage, or oversee funded maintainers

## The interface between the Project and maintainer funds

### What the Project offers

#### Recommended maintainer areas: where funded work would have the most impact

- The committee publishes areas where the Project is bottlenecked and where a funded maintainer would have multiplicative effect
- Informed by team lead input, Project Goals, and cross-team blocking patterns

#### Vetting and prioritizing applicants

- When a fund has candidates, the committee interviews, evaluates technical depth and community standing, and returns a prioritized list
- Applicant list is public; prioritized recommendations and individual feedback are confidential

#### Helping maintainers demonstrate their impact

- Through the Project Goals program, program managers, and reporting infrastructure
- Maintainers participate in Goals where relevant; the PM helps translate that into sponsor-facing summaries

### What the Project asks

#### Champion and reviewer bandwidth for priority areas

- As teams discuss Project Goals, they should be able to ask funded maintainers to champion goals the team considers a priority
- Funded maintainers aren't just working on their own interests — they're available to provide reviews, mentorship, and unblocking support where teams need it most

#### Support on urgent issues

- When a team has a regression or other urgent problem, they can ask funded maintainers to help
- "We have a regression, we need someone to fix this now" — funded maintainers are a resource teams can draw on

### What the Project does NOT do

- Contract with maintainers (the Project is not a legal entity)
- Make hiring decisions (we provide evaluation; funds decide)
- Manage performance (that's between the fund and the maintainer)
- Grant elevated privileges (funded maintainers have the same standing as any team member)

## How the Rust Foundation Maintainer Fund will work

This section describes how the RFMF will operate using the interface above. It also serves as a model that other maintainer funds are encouraged to follow.

### The committee that vets applicants is the Grants team

- Same body chartered by TC's Project Grants Program RFC: 5 members, LC-appointed, Launching Pad subteam
- Same people, same selection process, different funding pool
- Avoids creating parallel committees with overlapping membership

### The expected workflow: committee recommends, fund decides

- Committee publishes recommended areas
- RFMF forms a list of target areas for the call, drawing on both the committee's recommendations and sponsor preferences for where they'd like to see investment
- RFMF posts a call for applications in those target areas
- Committee vets applicants and returns a prioritized list
- RFMF will typically offer contracts to the top candidates on the list; if there are obstacles (salary expectations, availability, fit), they may reach further down
- The committee's role is evaluation and prioritization; the fund's role is making offers and closing contracts

### Broad applications, not cherry-picking

- The default is open calls where anyone can apply, with the committee providing a prioritized list
- Sponsors should not be selecting individual maintainers by name
- This prevents the failure mode where positions are filled entirely through personal networks

### Targeted maintenance: sponsors can fund a specific application area

- A sponsor that contributes enough funding can request a maintainer focused on a specific application area (e.g., networked systems, embedded, CLI tooling)
- The funding must cover both the targeted maintainer position AND a contribution to the open-ended maintenance pool described above
- The committee still vets and prioritizes applicants — the sponsor picks the area, not the person
- This gives sponsors a way to invest in the areas they care about while ensuring the broader maintenance needs aren't neglected

### Long-term contracts with self-directed senior maintainers

- Target people who already have deep Rust Project experience
- 12-month contracts with the expectation of renewal — long enough to make leaving another job worthwhile and to build the context that makes someone effective
- Before renewal, the fund gathers private feedback from the Project on how the maintainer's work is going; this informs the renewal decision but the fund makes the call
- Management is light-touch: start with self-directed people, accountability through the renewal cycle rather than day-to-day oversight
- The fund maintains enough reserves to offer 3–6 months of runway if funding dries up — maintainers shouldn't face a sudden cliff

### The money goes to maintainers

- Sponsor funds go primarily to maintainer contracts, with minimal overhead to cover the project management needed to coordinate the program
- The Foundation may require that sponsors at higher tiers be members of the Foundation in good standing

### Reporting flows through the Project Goals program

- Funded maintainers participate in Goals where their work aligns
- Program managers help prepare sponsor-facing summaries
- The Project provides the scaffolding; the fund uses it for sponsor relations

## How funders can help evolve Rust

This RFC establishes the maintainer-funding piece of a larger system. This section tells the complete story of how that system works, from a sponsor's first interest to shipped improvements.

### Find the application area that matches your interest

- The Project Goals program organizes work into application areas and roadmaps
- A funder identifies the area they care about — async networking, embedded, developer tooling, whatever fits their needs
- For funders who don't have a specific area, the general maintenance pool is always an option

### Ensure there's maintainer capacity to land the work

- The goals team checks whether the teams involved have enough reviewer and maintainer bandwidth to absorb new contributions
- If not, the funder directs funding to the RFMF (or another fund) with that application area as the targeted focus
- The RFMF hires a maintainer through the standard workflow: committee vets applicants, fund makes the final decision
- Even companies that already employ Rust maintainers benefit — their employees drive features, the funded maintainer provides the review substrate that lets those features land

### Fund contributors to drive specific goals

- Once maintainer capacity is in place, the goals team connects the funder with the roadmap's point-of-contact
- Together they identify which goals within the roadmap would benefit from funded contributors
- Contributors are funded through project grants, contracts, or other mechanisms — outside the RFMF's scope but part of the larger ecosystem

### The result: a coherent path from investment to impact

- Maintainers provide the review bandwidth and institutional knowledge
- Contributors drive the feature work and goal delivery
- The Project Goals program provides visibility into progress
- Sponsors see their investment turn into shipped improvements in the areas they care about

# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

## The committee: composition, selection, and responsibilities

- Defers to the LC's Project Grants Program RFC for committee composition, appointment process, conflict of interest rules, and governance structure
- This RFC adds RFMF-specific responsibilities: area recommendations and application vetting for funded maintainer positions

## Recommended areas process

- How areas are identified (team input, Goals data, cross-team blocking analysis)
- Publication mechanism and update frequency
- How sponsors can request additions (the "escape valve")

## Application vetting process

- What the committee evaluates: technical depth, community standing, maintenance orientation
- Interview process
- Confidentiality: what's public (applicant list, recommended areas) vs. confidential (prioritized recommendations, individual feedback)

## Relationship with Project Goals

- How funded maintainers integrate with the Goals process
- Reporting expectations: what the PM collects, what goes to sponsors, what's public
- How this differs from Goals reporting for volunteer contributors (it doesn't, much)

## Extending to other funds

- The interface described above is fund-agnostic
- LC evaluates new fund partnerships case-by-case
- Other funds may need different committee processes or different recommendation structures

# Frequently asked questions
[faq]: #faq

## Why an interface rather than a full program design?

- An earlier draft tried to specify tiers, compensation, contracts — the committee said that's the Foundation's domain
- Another draft only specified the Project's side — the committee said it didn't say enough about what the program actually is
- This RFC defines the interface and includes how the RFMF will use it as one instantiation

## Why reuse the Grants team rather than create a new committee?

- Avoids parallel bodies with overlapping membership and similar mandates
- The Grants team already has the selection infrastructure and LC appointment process

## Doesn't this give sponsors too much influence?

- Sponsors influence the *when*, not the *what* — they can request broad areas (async Rust) but not specific features or roadmap items
- The Project's decision-making processes are unchanged; funded work gets no privilege in technical discussions
- Sponsors still get value: their priorities move faster, they get visibility into outcomes

## Why not a flexible contractor pool instead of long-term maintainers?

- Context and trust take time to build
- The maintenance problems we heard about require sustained presence, not project-scoped interventions
- Contractors for scoped work is a valid model but a different program

## This adds work to people who are already stretched thin

- Committee members spend time on area recommendations and applicant vetting; team leads get consulted
- Program managers handle the operational coordination, keeping the burden on volunteers bounded
- The alternative — funds operating without Project input — leads to worse outcomes for everyone

## What if a funded maintainer underperforms?

- Performance management is the fund's responsibility, not the Project's
- The Project treats funded maintainers the same as any team member: Code of Conduct enforcement, team membership decisions
- The lines are clear: the Project evaluates candidates going in; the fund manages the relationship after

## What if sponsors want more influence than the axioms allow?

- The targeted maintenance path gives sponsors a way to pick an application area
- But sponsors don't pick people, don't direct technical decisions, and don't sit on the committee
- If that's not enough, the sponsor and the fund need to work it out — it's not the Project's problem to solve

## How does this work for companies that already employ Rust maintainers?

- Your maintainers are probably focused on feature work that maps to your business needs — that's rational, but it leaves a maintenance gap
- Contributing to the RFMF fills the substrate: review bandwidth, regression fixes, CI, the enabling work that makes *your* maintainers more productive too
- You can target an application area you care about while also funding the general pool

## How does this work for companies that want to invest in a specific area?

- Start with the Project Goals program — find the application area or roadmap that matches your interest
- The goals team checks whether there's enough maintainer capacity to absorb contributions in that area
- If not, direct funding to the RFMF with that area as the targeted maintenance focus
- Once capacity is in place, connect with the roadmap point-of-contact to fund contributors who will drive specific goals
- You get a coherent path from budget to results, with the Project coordinating the pieces

## How does this work for companies that just want to support Rust?

- Contribute to the RFMF's general maintenance pool
- The committee directs funding to wherever the Project is most bottlenecked
- Reporting through Project Goals gives you visibility into outcomes without requiring you to pick an area

## What about people who only want to work part time?

- This program targets long-term, sustained maintainers — the kind of commitment that's hard to do part time
- For contributors who want lighter-touch support, the LC's Project Grants Program ($1,500/month) is designed for exactly that
- The two programs are complementary: grants support a broad base of contributors; the RFMF funds deep, sustained maintenance work

## What happens if we don't do this?

- Funds operate without Project input on who to hire or where to focus
- More risk of misaligned funding — money going to visible features rather than invisible maintenance
- Teams continue to be precarious and isolated

# Prior art
[prior-art]: #prior-art

## Python Software Foundation: sponsors attach to people, not positions

- Lessons from 5 years of the Developer in Residence program
- Pure maintenance becomes draining; the 50/50 split "made all the difference"
- Different sponsors want different engagement levels

## Django Fellowship: weekly reports and community-focused maintenance

- Running since 2014; longer track record than PSF
- More focused on "housekeeping and community support"

## Zig Software Foundation: lean and independent

- Core team bills hours directly; 92% of spending goes to contributors
- Simpler model but smaller scale

## Scala Center: sponsor meetings as a selling point

- Sponsors send representatives to regular meetings — high value for selling the program internally
- University infrastructure provides stability but limits transferability

## TC's Project Grants Program: the committee model we're building on

- $100K, ~5 contributors at $1,500/month
- Grants team structure (5 members, LC-appointed, Launching Pad subteam) is the model for RFMF vetting
- Explicitly positions itself as "distinct from, but complementary to" the RFMF

# Unresolved questions
[unresolved-questions]: #unresolved-questions

## Before this RFC is accepted

- How often should the committee update recommended areas?
- What is the right turnaround time for application vetting?
- Should the committee's prioritized recommendations include written rationale, or just an ordered list?

## During implementation

- Detailed evaluation criteria for applicants
- Reporting templates and cadence
- How the "escape valve" for sponsor-requested areas works in practice

## Out of scope

- Compensation levels (fund's domain)
- Detailed contract terms — termination clauses, benefits, specific payment structures (fund's domain; the broad shape described in this RFC is an initial suggestion, subject to modification over time)
- How the Foundation solicits sponsors (Foundation's domain)
- Part-time vs. full-time arrangements (fund's domain)

# Future possibilities
[future-possibilities]: #future-possibilities

## Expansion to support earlier-career contributors

- Start with senior self-directed people; mentorship-focused positions could come later

## Portfolio funding model

- Assembling bundles of maintenance, refactoring, and feature work that map project needs to sponsor needs
- "The compiler team needs refactoring, sponsor 1 needs async, sponsor 2 needs interop — all three are met with a DiR on the type system"

## Coordination across multiple funds

- As more funds emerge, the interface may need mechanisms to avoid duplication or gaps

## Proactive needs identification

- Rather than waiting for Goals submissions, periodically surveying teams about maintenance needs
