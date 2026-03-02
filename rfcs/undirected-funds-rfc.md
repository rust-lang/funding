- Feature Name: `rust_maintainer_fund`
- Start Date: 2026-02-23
- RFC PR: [rust-lang/rfcs#0000](https://github.com/rust-lang/rfcs/pull/0000)

# Summary
[summary]: #summary

The Rust Foundation Maintainer Fund (RFMF) collects sponsorships from companies and individuals who want to support Rust's long-term health. Funds raised through the RFMF flow to the Leadership Council's Project Priorities budget. The Leadership Council determines how that budget is spent, deploying it through project grants, Maintainers in Residence, or other programs as needs evolve.

This RFC recommends that the primary use of RFMF funds should be hiring full-time Maintainers in Residence — experienced, self-directed maintainers who provide the sustained presence that teams need. This RFC describes what sponsors get in return for their contributions, how Maintainer in Residence candidates are selected, what's expected of them, and how the Foundation manages the relationship.

This RFC defines a Funding team charter: staying in contact with teams to understand their needs, connecting teams to available resources, and working with the Foundation to identify and/or vet candidates for Maintainer in Residence positions. The Foundation makes the final hiring decision and handles contracting, compensation, and sponsor relations.

[RFC 3919]: https://github.com/rust-lang/rfcs/pull/3919

### Topics for discussion

The following topics are not yet resolved and need committee input. Each has a corresponding FAQ entry with more detail.

1. **[Who manages Maintainers in Residence after they're hired?][who-manages-mirs]** The RFC currently places performance management with the Foundation. An alternative is to have the Project handle it through a dedicated (funded) resource. See the FAQ for tradeoffs.
2. **[Should the Funding team be a new team or extend the Grants team?][funding-team-org]** The RFC defines the charter but leaves organizational form to the Leadership Council. The Grants team has existing infrastructure but a narrower mandate; the Funding team charter is broader. See the FAQ for tradeoffs.

# Motivation
[motivation]: #motivation

The Rust Foundation is establishing a Maintainer Fund to collect sponsorships and provide long-term funding for Rust maintenance. Funds raised through the RFMF flow to the Leadership Council's Project Priorities budget, giving the Project control over how maintenance funding is deployed. The Leadership Council commissioned this RFC to recommend how those funds should be used. Our primary recommendation is that these funds should be used to hire full-time maintainers, called "Maintainers in Residence," though the Council retains flexibility to deploy funds through other programs as needs evolve.

## Why full-time maintainers in residence?

In preparing this recommendation, we interviewed team leads across the Project. The message was clear: *"what's needed is people with the focus to drive longer-scale projects."* Volunteer maintenance keeps the lights on, but larger-scale work — clearing review backlogs, driving cross-cutting refactors, carrying context across a complex codebase — stalls because nobody has the sustained focus to push it through. As one (volunteer) team lead said, *"All the time that reviewers have goes into reviewing, triaging, and so on, and then the interesting longer-term projects just fall under the table."*

The rust-analyzer experience shows what full-time presence makes possible, and what happens when it disappears:

* When a funded reviewer was working on r-a, the PR backlog stayed around 10. After that person changed jobs, it climbed to over 110: *"solving the review problem definitely requires money I think, there's no big question there."*
* Short-term grants help but aren't enough. The Clippy team received Foundation grants that let *"one person work almost full time on Clippy, but it was only for 6 months — it was hard to make long-term plans."*

The problems teams describe require sustained, long-term presence.

## Why companies should sponsor the maintainer fund

We expect two kinds of sponsors. First, individuals and organizations that value Rust and want to support its long-term health without any particular expectations. These will generally be smaller-dollar sponsors contributing to a project they believe in.

Second, and important for the fund's sustainability, are companies that employ developers or contributors working full-time to improve Rust. These companies are invested in Rust development, but their contributors' work still needs to be reviewed and landed by experienced maintainers. The incentive structures at most companies don't reward "general maintenance" like reviewing other people's PRs, mentoring newcomers, fixing regressions, and driving cross-cutting refactors. These activities don't advance any single company's goals, so they're hard to justify in a performance review and vulnerable to restructuring when priorities shift. Sponsoring the maintainer fund is a way for these companies to ensure the maintenance layer their contributors depend on stays healthy.

What do sponsors get in return (besides PR and good vibes)? First, a connection to the project: RFMF sponsors will meet with project leadership, team leads, and maintainers over the course of the year. This will help them stay abreast of what is happening in the project and also let the project hear from them about their needs and priorities. Experience at other language communities shows the importance of these efforts. The Scala Center experience shows that sponsors often value hearing from their peers — other Rust-using organizations — as much as they do hearing from the project itself. Knowing what is important to sponsors is good signal on what matters to users, but it's also important for maintaining a good relationship. As one Python Developer in Residence put it, *"In terms of how \[a Developer in Residence spends their time\], sponsors can't make them do anything, but if they care about a thing, and it'll make them renew the contract for another 12 months, good to know."* Sponsors can also reach out about specific PRs or bugs that need attention (this is best effort, not an SLA).

The project also highlights the work of funded maintainers via the content and project goals teams (these updates are made publicly available as well). Speaking with sponsors at the PSF confirms the importance of that kind of accountability: sponsors want to know what work would stop happening if they stopped funding. *"Very quickly that becomes the value prop when they are discussing internally whether to put in the $$."*

## Why the Project should drive the selection

A companion effort — the proposed Project Goals Funding program (see [Future possibilities][]) — would provide directed grants tied to specific goals, roadmaps, and application areas. But if we only fund goal-directed work, we miss a lot of what makes the Project healthy. Some teams don't directly deliver goals at all: moderation, infrastructure, release. Other work is cross-cutting and doesn't belong to any single goal but makes everyone's work go faster, such as major refactoring or CI improvements.

The RFMF exists to cover this gap. Its funds flow to the Leadership Council's Project Priorities budget, giving the Project control over how maintenance funding is deployed. But deciding where that funding has the most impact requires visibility into which teams are struggling, where dependencies are blocking, and where a single full-time person would have the most leverage, which is why we recommend that the Funding team (composed of active project members selected by the Leadership Council) drive the selection of who to award with a maintainer contract.

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

The RFMF collects sponsorships from companies and individuals and directs those funds to the Leadership Council's Project Priorities budget. The Council deploys these funds to maintain Rust's health — primarily through Maintainers in Residence, but also through project grants, travel funding, and other programs as needs dictate.

Maintainers in Residence are the flagship program: experienced, self-directed maintainers who do the work that keeps Rust healthy — reviews, design guidance, mentorship, unblocking, regressions, refactorings, and so forth. They are team members, not outsiders. They participate in team discussions, review PRs, mentor newcomers, and work on what the team needs. The difference is that they can commit sustained time to the work that volunteers can't.

## Design axioms

### The RFMF is a collaboration between the Project and the Foundation

The Project brings knowledge of team health and needs; the Foundation brings logistics, sponsor relationships, and operational capacity. The Funding team (see below) identifies which areas need support and works with the Foundation to select candidates. The Foundation makes the final hiring decision and handles contracting, compensation, and sponsor relations. This is a partnership, not a handoff — both sides contribute throughout.

### Engaging RFMF sponsors is a whole-project affair

The Leadership Council, team leads, and Maintainers in Residence all participate in sponsor engagement — attending meetings, discussing project direction, and learning about sponsor pain points. This benefits everyone: sponsors get a direct connection to the people doing the work, and the project learns firsthand what Rust-using organizations need. Sponsor engagement does not imply that any technical decisions (RFC approvals, PR reviews, design choices) should be made differently than they would be otherwise.

### Maintainers are team members, not outsiders

Maintainer in Residence candidates must already be members of the relevant Rust team(s) with the permissions needed for the work — reviewing PRs, championing goals, and performing actions limited to official team members. This is a hard requirement, not just an expectation. Funded maintainers are not a separate class of contributor — they're existing team members who can now commit sustained time.

### Not one size fits all

The RFMF doesn't try to be the sole channel for funding Rust maintenance. The Maintainer in Residence program fills a specific role: allowing project teams to select and direct maintainers toward the areas they identify as most critical. Other structures — the proposed Project Goals Funding program for directed grants (see [Future possibilities][]), the Project Grants Program for contributor stipends, the Rust-Analyzer Open Collective, the proposed RustNL Maintainer Fund, company employment — serve complementary roles.

### The Project helps maintainers demonstrate their impact

The Project provides scaffolding — goals, program management, reporting infrastructure — so maintainers can focus on the work while sponsors get visibility into outcomes.

## What sponsors get
[what-sponsors-get]: #what-sponsors-get

RFMF sponsors contribute to a general fund and don't direct where the money goes or who gets hired. Every contribution helps fund the sustained maintenance that keeps Rust healthy. All sponsors receive public recognition and visibility into how funds are being used through regular public reports.

The Foundation should establish sponsorship tiers to encourage larger contributions and year-over-year commitment, as sustained sponsorship permits more stability for the program. Higher tiers provide additional benefits:

* **A community of sponsors.** The Foundation builds a community of sponsoring organizations. Sponsors meet regularly with project leadership (Leadership Council, team leads), maintainers, and each other. The Scala Center experience shows that sponsors often value hearing from their peers — other Rust-using organizations — as much as they do hearing from project leadership itself.
* **Regular engagement with project leadership and maintainers.** Meetings with Leadership Council members, team leads, and Maintainers in Residence to discuss project direction, sponsor experiences, and pain points. Maintainers also benefit from these meetings — they learn firsthand what sponsors need, which informs their priorities naturally.
* **Best-effort attention.** Sponsors can reach out to the Foundation or project contacts about PRs or bugs that need attention. There is no SLA or guarantee — any maintainer would bump a bug report from an active user, and sponsors can reasonably expect the same consideration.

This RFC does not define the tiers — that is the Foundation's domain.

The Leadership Council and Rust team members are generally expected to participate in sponsor engagement activities — attending meetings, having discussions with sponsors — as it is in the project's overall interest to encourage sponsorship. This does not imply that team members should make any technical decisions (e.g., RFC or PR approvals) that they would not have made otherwise. The project also benefits from closer contact with sponsoring organizations: they are by definition Rust-using organizations that value open-source maintenance, and it is helpful to learn about their pain points, successes, and other lessons.

What sponsors do not get: the ability to direct a maintainer's work, pick who gets hired, bypass project processes, or influence technical decisions.

## The Funding team

This RFC defines a set of responsibilities we call the "Funding team" charter:

1. **Staying in regular contact with teams** to understand their needs and the state of the project.
2. **Connecting teams to available resources** even outside MiR hiring — e.g., redirecting an existing maintainer to help with a situation, connecting a team lead to the Foundation, etc.
3. **Working with the Foundation to select MiR candidates** when positions become available, choosing candidates who'll have the most overall impact based on project needs.

This RFC defines the charter — the responsibilities — but leaves the organizational structure to the Leadership Council. The Funding team could be a new team, or it could be an extension of the existing Grants team established by [RFC 3919]. See [Unresolved questions][] for more discussion.

## Full-time positions with balanced expectations

Maintainers in Residence are expected to spend 100% of their funded time working to improve the Rust project. Within that:

* ~50% on **team priorities** — whatever the team needs. This could be development work (refactoring a major subsystem, rewriting the trait solver) or reactive work (reviews, mentoring, bug-fixing, triage).
* ~50% on **individual priorities of their choosing** within the project.

This split is about team-directed vs. self-directed, not "maintenance vs. features." If the team needs the trait solver rewritten, that's team priorities. The PSF's experience after nearly five years confirms that allowing this balance "made all the difference" — pure maintenance work becomes draining over time.

# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

## The Funding team

The Funding team's role is to keep a pulse on the project and work with the Foundation to select which maintainers to hire. Its core responsibilities are:

1. **Staying in regular contact with teams** — meeting regularly with team leads and members to understand their needs, health, and where support would have the most impact.
2. **Connecting teams to available resources** — even outside MiR hiring. This might mean redirecting an existing maintainer to help with a situation, connecting a team lead to the Foundation, or surfacing resources a team didn't know existed.
3. **Working with the Foundation to select MiR candidates** — when positions become available, evaluating applicants and selecting candidates who'll have the most overall impact based on project needs.

The Funding team does not make hiring decisions; that is the Foundation's domain. The Funding team also does not manage funded maintainers after they're hired; its role ends with the selection.

## Application and vetting process

The process of contracting a new Maintainer in Residence begins with an open call for applications. Anyone can apply — broad applications help surface needs and candidates the Funding team might not have identified on its own. However, successful candidates must already be members of the relevant Rust team(s) with the permissions needed for the work.

Applicants provide a summary of their experience with the Rust project along with a high-level description of the kind of work they would like to do. This description can be quite general (e.g., "maintain rustfmt") but could also be specific (e.g., "refactor the codebase to be more accessible").

The Funding team prioritizes applications based on:

1. conversations with team leads and team members to assess what support is most urgently needed;
2. the applicant's history with the project;
3. any specific work that was proposed in the application;
4. the results of interviews or conversations with the applicant; and
5. any history of interpersonal or Code-of-Conduct issues known to the moderation team.

The Funding team evaluates applicants on three dimensions: technical depth in the relevant area, community standing and trust within the Project, and sustained work orientation (whether the candidate's track record suggests they'll thrive in a role focused on reviews, mentorship, unblocking, and the kind of long-term technical work that requires deep context).

The Funding team works with the Foundation to select from the applicant pool. The Foundation makes the final decision on who receives the contract, but the expectation is that it will follow the Funding team's recommendation. There may be practical reasons (salary expectations, availability, fit) that lead to a different choice. The fact that applications are open is public; the prioritized recommendations and individual feedback are confidential between the Funding team and the Foundation.

## Contract terms and renewal

The precise terms of the arrangement are not defined by this RFC. The arrangement is likely to begin as year-long contracts but may change to other durations, regular employment, or vary by locale. The important points are: it is a **full-time position**, and it is expected to **continue as long as both sides are satisfied and funding is available**. Compensation should be a flat rate within a small number of bands (e.g., junior and senior), rather than individually negotiated. Flat rates keep the program simple and avoid the perception that some maintainers are valued more than others for equivalent work. The compensation structure is publicly advertised as part of the call for applications. The Foundation determines the specific rates and may adjust them over time as the program learns what works and what's needed to attract strong candidates.

Renewal is not guaranteed:

* There may not be adequate funds available to continue the existing maintainer contracts.
* The Funding team may feel that there are urgent unmet needs within the project that prompt a change in maintainer (but this is in tension with the primary goal of this RFC of providing long-term, funded maintenance; see below).
* The maintainer may not be doing an adequate job (though this scenario is typically managed separately; see performance management below).

Deciding not to renew a well-performing maintainer in order to fund a different area should not be done lightly. Sustained presence is the core value proposition of the program — startup overhead is real, context takes time to build, and the problems this program targets require continuity. The Funding team should strive to maintain existing maintainers and grow the program to meet new needs rather than redirecting existing positions. Given limited funding, the Funding team can also encourage existing maintainers to pick up work in new areas rather than replacing them.

In advance of contract renewal, the Foundation will consult with the Funding team. The Funding team will assess the needs of the project and decide whether a change should be made. If they do decide to change things, they will issue a new call for applications. If desired, the current maintainer may re-apply.

## Maintainer in Residence expectations

Maintainers in Residence are expected to spend 100% of their funded time working to improve the Rust project. Within that:

* ~50% on **team priorities** — whatever the team identifies as most important. This includes reviews, mentoring, bug-fixing, triage, and larger development work like refactors or subsystem rewrites.
* ~50% on **individual priorities of their choosing** within the project.

Maintainers in Residence are also expected to:

* resolve time-critical issues such as newly reported bugs;
* champion Project Goals supported by their respective teams, even if they themselves might not have championed that goal as an individual;
* work with the Project to ensure their work gets regularly reported on;
* remain a member of the Project and relevant teams, in good standing.

## Responding to sponsor requests

Sponsors can reach out to the Foundation or project contacts about PRs or bugs that need attention. This is best effort, not an SLA — any maintainer would bump a bug report from an active user, and sponsors can reasonably expect the same consideration.

Requests that go beyond this — "develop this feature" or "devote sustained time to our priority" — are outside the scope of this relationship. (The [Future possibilities][] section describes a Project Goal Funding program that could support sponsors seeking that level of direction in the future.) The Foundation manages sponsor expectations and serves as a buffer so that maintainers aren't negotiating these boundaries directly.

## Reporting and impact visibility

Funded maintainers participate in the Project Goals process the same way any other team member does. If they champion a goal, they show up in the goal's tracking and reporting. If they provide review bandwidth for a goal, that's reflected in the goal's progress updates. There is no separate reporting track for funded maintainers; the Goals program is the reporting infrastructure.

To ensure continued funding, it is important that the RFMF is able to demonstrate impact and value to its sponsors. The entire Project has a stake in maintainers demonstrating impact, and other teams are expected to assist:

* The program management team will prepare an initial draft by examining GitHub activity (PR reviews, etc.) and via updates on Project Goals championed by the maintainer.
* The Content team will interview maintainers and highlight their work.

Program managers collect progress updates from goal owners (funded or not) on a regular cadence and prepare summaries. For funded maintainers, these summaries serve double duty: they give the Project visibility into goal progress, and the Foundation can use them to prepare sponsor-facing reports.

The reporting expectations for funded maintainers are not more onerous than for volunteer contributors. The point is to reduce burden, not add it.

## Performance management

The Foundation staff and the Funding team will monitor the maintainer's work and periodically solicit feedback from contributors and other team members. If they do not feel that a maintainer is doing a good job, Foundation staff are expected to provide constructive feedback to the maintainer. If the maintainer's performance does not improve, their contract will not be renewed.

Separately, Code of Conduct violations that result in removal from the Project immediately terminate the contract. Team membership is a hard requirement for the role; a maintainer who is no longer a project member cannot continue as a Maintainer in Residence.

The Project does not decide whether a contract gets renewed; it provides input.

# Frequently asked questions
[faq]: #faq

## How will the Funding team be organized?
[funding-team-org]: #how-will-the-funding-team-be-organized

This RFC defines the Funding team's charter — its responsibilities — but leaves the organizational structure to the Leadership Council. There are two main options:

**Extend the Grants team.** The Grants team established by [RFC 3919] already has an LC appointment process, selection infrastructure, and conflict-of-interest policies. Extending it avoids fragmenting volunteer attention across overlapping committees.

**Create a new team.** The Funding team's charter is broader than selecting recipients — it includes staying in regular contact with teams, connecting them to resources, and understanding project health holistically. MiR selection is only one part of that mandate. A new team with a broader mandate may be a better fit than extending a team whose focus is choosing grant recipients.

We expect the Leadership Council to determine the right organizational form.

## What does it look like to have a Maintainer in Residence on my team?

In one sense, the same as having any other team member. They show up in reviews, participate in design discussions, mentor newcomers, and work on what the team needs. The PSF's experience after nearly five years is instructive: the Developer in Residence does roughly 50/50 maintenance and proactive work, and the role feels like "just another team member" rather than an outside presence.

But there is an important difference beyond just having more time. Most team members are volunteers, and team leads can't ask volunteers to take on specific tasks — they can only hope someone steps up. A Maintainer in Residence, by contrast, has dedicated half their time to team priorities. Team leadership should feel free to ask a MiR to take on high-priority work that nobody else can tackle — championing a goal, driving a critical refactor, clearing a review backlog — so long as it fits within that team-priorities capacity. This is a resource that team leads have never had before, and it changes the dynamic from "hoping someone volunteers" to "directing sustained effort where it's needed most."

## Why not a flexible contractor pool instead of long-term maintainers?

Context and trust take time to build. The maintenance problems we heard about in team lead interviews (review backlogs, cross-team blocking, complex refactors that need months of sustained attention) require sustained presence, not project-scoped interventions. Contractors for scoped work is a valid model, but it's a different program solving a different problem.

## How will we find the people for the Funding team?

The same way we find people for any other team. Funding team work is expected to be rewarding, as it gives team members the opportunity to understand the project holistically and support one another.

## Who manages Maintainers in Residence after they're hired?
[who-manages-mirs]: #who-manages-maintainers-in-residence-after-theyre-hired

The Funding team's role ends with the recommendation. Someone needs to synthesize feedback from the Project and make the call on performance. There are two main options:

**Foundation manages (current RFC position).** Management and performance feedback are skills, and the Foundation has professional staff experienced in them. This shouldn't be a heavy lift early on — we're selecting experienced, self-directed maintainers who are unlikely to have significant performance issues. The Foundation gathers input from the Project (team leads, collaborators) and synthesizes it. This may need to evolve as the program scales.

**Project manages.** The Project has deeper technical context to evaluate whether work is landing well. But Project-side management means either a volunteer committee handles it (likely unskilled at management, outside the Funding team's competency) or a dedicated person is hired for it (high overhead relative to the program size, especially early on).

## What if a Maintainer in Residence underperforms?

Performance management is the Foundation's responsibility, not the Project's. The Project treats funded maintainers the same as any team member: Code of Conduct enforcement, team membership decisions, and the normal expectations that come with being on a team. The lines are clear: the Project evaluates candidates going in; the Foundation manages the relationship after. (See also [Who manages Maintainers in Residence after they're hired?][who-manages-mirs] for discussion of alternatives.)

## What about people who only want to work part time?

The RFMF targets long-term, sustained maintainers, the kind of commitment that's hard to do part time. For contributors who want lighter-touch support, the LC's Project Grants Program ([RFC 3919], $1,500/month) is designed for exactly that. The two programs are complementary: grants support a broad base of contributors; the RFMF funds deep, sustained maintenance work.

## What about sponsors who want to pay for a particular item to get done?

That's outside the scope of the RFMF, which is undirected funding — sponsors contribute to a general fund and the Leadership Council decides how to deploy it. A companion effort, the proposed Project Goals Funding program (see [Future possibilities][]), is designed for exactly this: sponsors direct funding at specific Project Goals, and the Foundation issues grants to advance that work. Sponsors seeking that level of direction should look there rather than the RFMF.

## What does this RFC deliberately not specify?

This RFC defines how the RFMF collects sponsorships, what kinds of things sponsors receive in return, and how the Project and Foundation work together to select and manage Maintainers in Residence. It deliberately does not specify how much funding the RFMF has, specific sponsorship tier structures, or detailed solicitation strategy. It also leaves operational details to the Foundation: compensation levels, detailed contract terms, evaluation criteria specifics, and reporting templates. How the Project Priorities budget is spent is determined by the Leadership Council. The broad shape described here is a recommendation, subject to modification over time as the program learns what works.

## What happens if we don't do this?

The Foundation will still operate its fund, but without structured Project input on who to hire or where to focus, and without a clear channel for funds to flow to the Project Priorities budget. There is more risk of misaligned funding, with money going to visible features rather than the invisible maintenance work that keeps Rust healthy. Teams continue to be precarious and isolated, and the Project misses the chance to build a coordination layer that connects willing sponsors to the work that needs doing.

# Prior art
[prior-art]: #prior-art

## Python Software Foundation: lessons from a mature program

The PSF started its Developer in Residence program in 2021. After nearly five years, it now funds multiple maintainers, each sponsored by a specific company (Meta, Bloomberg, Alpha-Omega, Vercel, among others). Contracts are for 12 months, renewable based on continued sponsor funding. Maintainers are employees or contractors of the PSF, reporting to both the Executive Director and the Steering Council.

The program's evolution taught us several lessons we've incorporated into this RFC. First, pure maintenance work becomes draining over time. The first Developer in Residence started doing only reviews, backports, and CI, and found that after a year or two, "there's not much joy in that." Allowing feature work alongside maintenance "made all the difference." We've reflected this in the RFMF design: Maintainers in Residence split their time roughly 50/50 between team priorities and individual priorities of their choosing, rather than being assigned purely to maintenance.

Second, sponsors attach to people, not positions. In practice, a sponsor funding a position filled by a particular person will want to continue sponsoring that person specifically if they're happy with the work, rather than funding an abstract role. This has implications for how the Foundation thinks about sponsor relationships: sponsors care about outcomes and the people producing them.

One key difference between the PSF model and what we propose: the PSF ties each position to a specific sponsor, while the RFMF pools sponsorships and the Project decides how to allocate them. Pool funding gives the Project more flexibility — it can fund positions based on where the need is greatest rather than where a particular sponsor's interest lies, and it can sustain positions even if an individual sponsor drops out. The Scala Center provides precedent that a pool-funded model can work: sponsors contribute to a general fund at tiered levels, and the Center decides how to allocate it — an Advisory Board of sponsors makes non-binding recommendations on priorities, and the Center's leadership decides on execution and hiring. That said, we may need to adjust if pool funding proves difficult to raise — the PSF's experience shows that earmarked sponsorship can be an easier sell. The Foundation should be prepared to adapt.

Third, different sponsors want very different levels of engagement. Some are hands-off; others want detailed quarterly reports and input on how maintainers spend their time. The Foundation as an intermediary is valuable here. It buffers the relationship between sponsors and maintainers, so that maintainers aren't managing sponsor expectations directly.

## Django Fellowship: weekly reports and community-focused maintenance

The Django Fellowship program has been running since 2014, predating the PSF program and providing the longest track record of any comparable effort. Fellows are contractors (not employees) who post weekly reports. The work is focused on "housekeeping and community support": monitoring security email, fixing release blockers, reviewing pull requests, and mentoring new contributors.

The program originally required a minimum of 20 hours per week, with compensation described as "not competitive with full-time salaries in big cities." Over time it has evolved: the program now has three Fellows, some working full-time, with compensation adjusted annually. The Django model demonstrates that a maintenance-focused role can work long-term, and that programs naturally evolve toward more hours and more competitive compensation as they prove their value — a trajectory we expect the RFMF to follow as well, starting with full-time positions from the outset.

## Zig Software Foundation: lean and independent

The ZSF takes a simpler approach: core team members bill hours directly to the foundation. As a 501(c)(3) non-profit founded in 2020, 92% of its spending goes directly to paying contributors, with minimal administrative overhead. It has no big tech companies on its board, an explicit design choice to maintain independence.

The ZSF model is leaner and more informal than PSF or Django, but also smaller in scale and more dependent on individual large donations. It demonstrates that low-overhead models are possible, but the approach may not scale to the number of maintainers Rust needs.

## Scala Center: pool-funded with sponsor engagement

The Scala Center, housed at EPFL, takes a pool-funded approach that contrasts with the PSF's per-sponsor-per-position model. Corporate sponsors contribute to a general fund at tiered levels and send representatives to quarterly Advisory Board meetings. The Advisory Board makes non-binding recommendations on priorities; the Center's leadership decides on execution and hiring. Sponsors influence direction through discussion but don't direct specific positions or hires.

Two aspects of the Scala Center model have been particularly influential on this RFC. First, the sponsor meeting structure: sponsors meet regularly with maintainers and with each other, and these meetings have been described as a "big win" for selling the program internally. Having sponsor representatives commit to attend regular meetings makes the program legible to upper management. Second, sponsors often value hearing from their peers — other organizations using the language — as much as from the project itself. Both of these insights shaped the RFMF's sponsor engagement design.

The Scala Center employs engineers directly as university employees, which provides stability but depends on university infrastructure. That structural detail doesn't transfer to Rust, but the pool-funding model and sponsor engagement approach do. The Scala Center demonstrates that sponsors will contribute to a general fund without earmarking, provided they get meaningful engagement in return.

## TC's Project Grants Program: a related committee model

The Leadership Council's Project Grants Program ([RFC 3919]) establishes a $100K program supporting ~5 contributors at $1,500/month. It charters a Grants team (5 members, LC-appointed, organized as a Launching Pad subteam) to select recipients and oversee the program. The RFC explicitly positions itself as "distinct from, but complementary to" the RFMF: grants are smaller-scale, flexible, Project-controlled support, while the RFMF targets larger-scale, sustained maintenance.

The Grants team's charter overlaps significantly with the Funding team charter we define here — both involve assessing project needs and selecting candidates. The Leadership Council may choose to extend the Grants team with the Funding team's responsibilities rather than creating a separate body, which would avoid fragmenting the Project's attention across multiple committees with overlapping mandates.

# Unresolved questions
[unresolved-questions]: #unresolved-questions

## Organizational form of the Funding team

This RFC defines the Funding team's charter — its responsibilities — but leaves the organizational structure to the Leadership Council. The Funding team could be a new team, or it could be an extension of the existing Grants team established by [RFC 3919]. Future possibilities include merging the two teams or generalizing the Funding team into a broader team for supporting Rust teams. We expect the Leadership Council to determine the right organizational form.

# Future possibilities
[future-possibilities]: #future-possibilities

## Extending the vetting service to other funding organizations

The clearest message from our team lead interviews was that the most effective way to help teams is to add full-time, long-term maintainers. Short-term grants and scoped contracts have their place, but the problems teams described — review backlogs, cross-cutting refactors, carrying context across a complex codebase — require sustained presence. We encourage any organization looking to fund Rust maintenance to direct funding toward long-term Maintainer in Residence positions.

This RFC defines the interface between the Rust Project and the RFMF specifically, but nothing about the process is inherently RFMF-specific. The Funding team's core service — assessing where full-time maintainers would have the most impact, evaluating candidates, and selecting the best candidates — could be offered to other funding organizations that want to hire Maintainers in Residence. The value proposition is the same regardless of who's paying: the Project has visibility into which teams are struggling and which candidates have the trust and context to be effective, and funding organizations benefit from that assessment rather than making hiring decisions without it.

## Project Goals Funding program

The RFMF provides undirected funding — sponsors contribute to a general fund and the Leadership Council decides how to deploy it. There are ongoing plans to propose a Project Goals Funding program that would allow sponsors to direct funding at specific Project Goals. Sponsors would choose goals, roadmaps, or application areas to fund, and the Foundation would issue grants to contributors working on that work. A fixed percentage of directed funding (likely 10% to start) would flow to the Leadership Council's Project Priorities budget, where it can be used to fund maintenance, project management, or other activities. Together, the two programs cover the full spectrum of sponsor needs: undirected funding for those who want to support Rust's overall health, and directed funding for those who want to accelerate specific work.
