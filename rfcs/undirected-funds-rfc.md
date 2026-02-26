- Feature Name: `rust_maintainer_fund`
- Start Date: 2026-02-23
- RFC PR: [rust-lang/rfcs#0000](https://github.com/rust-lang/rfcs/pull/0000)

# Summary
[summary]: #summary

The Rust Foundation Maintainer Fund (RFMF) is a joint effort by the Rust Project and the Rust Foundation to fund full-time Rust maintainers, called Maintainers in Residence. This RFC proposes how the Maintainer in Residence program should work: how candidates are selected, what's expected of them, and how the Foundation manages the relationship.

This RFC builds on the Grants team established by [RFC 3919]. This RFC extends the Grants team's role to also vet candidates for Maintainer in Residence positions funded through the RFMF. The Grants team identifies which areas need support and returns a prioritized recommendation to the Foundation; the Foundation makes the final hiring decision and handles contracting, compensation, and funder relations.

This RFC does not specify how much funding the RFMF has or where that funding comes from. It describes how the Project and Foundation would work together to make the best use of whatever funding is available for Maintainer in Residence positions.

[RFC 3919]: https://github.com/rust-lang/rfcs/pull/3919

# Motivation
[motivation]: #motivation

The Rust Foundation is establishing a Maintainer Fund to provide long-term funding for full-time Rust maintainers. The Leadership Council commissioned this RFC to recommend how those funds should be used. Our recommendation is that these funds should be used to hire full-time maintainers, called "Maintainers in Residence". 

## Why full-time maintainers in residence?

In preparing this recommendation, we interviewed team leads across the Project. The message was clear: *"what's needed is people with the focus to drive longer-scale projects."* Volunteer maintenance keeps the lights on, but larger-scale work — clearing review backlogs, driving cross-cutting refactors, carrying context across a complex codebase — stalls because nobody has the sustained focus to push it through. The Clippy team put it simply: *"all the time that reviewers have goes into reviewing, triaging, and so on, and then the interesting longer-term projects just fall under the table."*

The rust-analyzer experience shows what full-time presence makes possible — and what happens when it disappears. When a funded reviewer was working on r-a, the PR backlog stayed around 10. After that person changed jobs, it climbed to over 110: *"solving the review problem definitely requires money I think, there's no big question there."* Short-term grants help but aren't enough — the Clippy team received Foundation grants that let *"one person work almost full time on Clippy, but it was only for 6 months — it was hard to make long-term plans."* The problems teams describe require sustained, long-term presence.

## Why companies should fund the maintainer fund

We expect two kinds of donors to this fund. First, individuals and organizations that value Rust and want to support its long-term health — these are generally smaller-dollar donors contributing to a project they believe in.

Second, and likely the larger source of funding, are companies that employ developers or contributors working full-time to improve Rust. These companies already invest in Rust development, but their contributors' work still needs to be reviewed and landed by experienced maintainers. The incentive structures at most companies don't reward "general maintenance" — reviewing other people's PRs, mentoring newcomers, fixing regressions, driving cross-cutting refactors. These activities don't advance any single company's goals, so they're hard to justify in a performance review and vulnerable to restructuring when priorities shift. Sponsoring the maintainer fund is a way for these companies to ensure the maintenance layer their contributors depend on stays healthy.

What do funders get in return? Maintainers are always prioritizing — there are always more PRs to review, more bugs to triage, more work than time. Funders can reasonably expect that their bug reports get looked at, their PRs get reviewed, and their questions get answered. This costs the project essentially nothing: it's reprioritization within work the maintainer would do anyway. The PSF's experience after five years of its Developer in Residence program confirms that this kind of influence is normal and healthy. As one of their Developers in Residence put it when asked about sponsors influencing prioritization: *"Yes, of course, and I think that is entirely ethical."* Bloomberg, one of the PSF's sponsors, gives active feedback on how their sponsored maintainer spends time — *"they can't tell him that he MUST, but if they care about a thing, and it'll make them renew the contract for another 12 months, good to know."*

The boundary is clear: funders can influence prioritization, but they can't direct the work or bypass project processes. No amount of sponsorship makes an RFC get accepted or a design decision go a particular way.

## Why the Project should drive the selection

Other funding mechanisms exist (or are being proposed) to fund development work that ties clearly to Project Goals roadmaps. But if we only fund goal-directed work, we miss a lot of what makes the Project healthy. Some teams don't directly deliver goals at all: moderation, infrastructure, release. Other work is cross-cutting and doesn't belong to any single goal but makes everyone's work go faster, such as major refactoring or CI improvements.

The RFMF exists to cover this gap. But deciding where that funding has the most impact requires visibility into which teams are struggling, where dependencies are blocking, and where a single full-time person would have the most leverage, which is why we recommend that the Grants team (composed of active project members selected by the leadership council) drive the selection of who to award with a maintainer contract.

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

The RFMF funds experienced, self-directed Maintainers in Residence who do the work that keeps Rust healthy: reviews, design guidance, mentorship, unblocking, regressions, refactorings, and so forth.

Maintainers in Residence are team members, not outsiders. They participate in team discussions, review PRs, mentor newcomers, and work on what the team needs. The difference is that they can commit sustained time to the work that volunteers can't.

## Design axioms

### The Project vets, the Foundation hires

The RFMF is a joint effort. The Grants team (established by [RFC 3919]) identifies which areas need support, vets applicants, and returns a prioritized recommendation to the Foundation. The Foundation makes the final hiring decision and handles contracting, compensation, and funder relations. This separation keeps the Project focused on technical judgment and the Foundation focused on operational execution.

### Funders get prioritization, not direction

Funders can reasonably expect that their bug reports, PRs, and questions get attention — this is reprioritization within work the maintainer would do anyway, and it costs the project essentially nothing. What funders cannot do is direct a maintainer's work or bypass project processes. Maintainers in Residence decide how to spend their time based on what they and their teams think is most important.

### Maintainers are team members, not outsiders

Funded maintainers participate in team discussions, review PRs, mentor newcomers, and work on what the team needs. They are not a separate class of contributor — they're team members who can commit sustained time.

### Not one size fits all

The RFMF doesn't try to be the sole employer of funded Rust maintainers. The Maintainer in Residence program fills a specific role: allowing project teams to select and direct maintainers toward the areas they identify as most critical. Other structures — the Rust-Analyzer Open Collective, the proposed RustNL Maintainer Fund, company employment — serve complementary roles.

### The Project helps maintainers demonstrate their impact

The Project provides scaffolding — goals, program management, reporting infrastructure — so maintainers can focus on the work while funders get visibility into outcomes.

## The Grants team

The Grants team chartered by [RFC 3919] — five members, appointed by the Leadership Council, organized as a Launching Pad subteam — takes on vetting Maintainer in Residence candidates as an additional responsibility alongside its existing grants work. This avoids creating parallel committees with overlapping membership and similar mandates.

## Long-term contracts focused on maintenance, but with time for exploration

Contract terms are expected to be around one year with annual renewal, though exact terms can be customized to the circumstance. Maintainers are expected to devote approximately half their time to maintenance in their area of focus, with the other half for work of their choosing.

# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

## The Grants team

The Grants team's Maintainer in Residence responsibilities are: staying on top of the state of the Project by meeting regularly with teams and team leads, vetting applicants, and providing a prioritized recommendation list to the Foundation. This ongoing contact helps them assess where and how funds should be distributed. The Grants team does not make hiring decisions; that is the Foundation's domain. The Grants team also does not manage funded maintainers after they're hired; its role ends with the recommendation.

## Application and vetting process

The process of contracting a new Maintainer in Residence begins with an open call for applications. Anyone can apply. Broad applications help surface needs and candidates the Grants team might not have identified on its own.

Applicants provide a summary of their experience with the Rust project along with a high-level description of the kind of work they would like to do. This description can be quite general (e.g., "maintain rustfmt") but could also be specific (e.g., "refactor the codebase to be more accessible").

The Grants team prioritizes applications based on:

1. conversations with team leads and team members to assess what support is most urgently needed;
2. the applicant's history with the project;
3. the work that was proposed;
4. the results of interviews or conversations with the applicant; and
5. any history of interpersonal or Code-of-Conduct issues known to the moderation team.

The Grants team evaluates applicants on three dimensions: technical depth in the relevant area, community standing and trust within the Project, and maintenance orientation (whether the candidate's track record suggests they'll thrive in a role focused on reviews, mentorship, unblocking, and sustained technical work rather than feature implementation).

The resulting prioritized list is returned to the Foundation. The final decision on who receives the contract is made by the Foundation staff. The expectation is that the Foundation will take the top candidate(s), but this is not a strict requirement. There may be practical reasons (salary expectations, availability, fit) to reach further down the list. The fact that applications are open is public; the prioritized recommendations and individual feedback are confidential between the Grants team and the Foundation.

## Contract terms and renewal

Contract terms are expected to be 1-year and to be renewed year-over-year, though exact terms can be customized to the circumstance. This is long enough to make leaving another job worthwhile and to build the context that makes someone effective. The PSF's experience confirms that contracts of this length with annual renewal provide reasonable stability while keeping the fund flexible.

Renewal is not guaranteed:

* There may not be adequate funds available to continue the existing maintainer contracts.
* The Grants team may feel that there are urgent unmet needs within the project that prompt a change in maintainer.
* The maintainer may not be doing an adequate job (though this scenario is typically managed separately; see performance management below).

In advance of contract renewal, the Foundation will consult with the Grants team. The Grants team will assess the needs of the project and decide whether a change should be made. If they do decide to change things, they will issue a new call for applications. If desired, the current maintainer may re-apply.

## Maintainer in Residence expectations

Maintainers in Residence are expected to:

* devote approximately half of their paid time to *maintenance* in their area of focus, with the other half being for work of their choosing;
* resolve time-critical issues such as newly reported bugs;
* champion project goals supported by their respective teams.

## Responding to funder requests

As described in the [motivation][motivation], funders can reasonably expect prioritization: a bug report looked at, a PR reviewed, a question answered. This is reprioritization within work the maintainer would do anyway — any maintainer would bump a bug report from an active user.

Requests that go beyond prioritization — "develop this feature" or "devote sustained time to our priority" — are outside the scope of this relationship. The Foundation manages funder expectations and serves as a buffer so that maintainers aren't negotiating these boundaries directly.

## Reporting and impact visibility

Funded maintainers participate in the Project Goals process the same way any other team member does. If they champion a goal, they show up in the goal's tracking and reporting. If they provide review bandwidth for a goal, that's reflected in the goal's progress updates. There is no separate reporting track for funded maintainers; the Goals program is the reporting infrastructure.

To ensure continued funding, it is important that the RFMF is able to demonstrate impact and value to its funders. The entire Project has a stake in maintainers demonstrating impact, and other teams are expected to assist:

* The Goals team will prepare an initial draft by examining GitHub activity (PR reviews, etc.) and via updates on project goals championed by the maintainer.
* The Content team will interview maintainers and highlight their work.

Program managers collect progress updates from goal owners (funded or not) on a regular cadence and prepare summaries. For funded maintainers, these summaries serve double duty: they give the Project visibility into goal progress, and the Foundation can use them to prepare funder-facing reports.

The reporting expectations for funded maintainers are not more onerous than for volunteer contributors. The point is to reduce burden, not add it.

## Performance management

The Foundation staff and the Grants team will monitor the maintainer's work and periodically solicit feedback from contributors and other team members. If they do not feel that a maintainer is doing a good job, Foundation staff are expected to provide constructive feedback to the maintainer. If the maintainer's performance does not improve, their contract will not be renewed, and in extreme cases (e.g., code-of-conduct violations) could be terminated early. The Project does not decide whether a contract gets renewed; it provides input.

# Frequently asked questions
[faq]: #faq

## Why reuse the Grants team rather than create a new committee?

Creating a new committee would mean a parallel body with overlapping membership and a similar mandate. The Grants team already has selection infrastructure and an LC appointment process. Adding RFMF-specific responsibilities to the same team is simpler and avoids fragmenting attention.

## What does it look like to have a Maintainer in Residence on my team?

The same as having any other team member. They show up in reviews, participate in design discussions, mentor newcomers, and work on what the team needs. The PSF's experience after nearly five years is instructive: the Developer in Residence does roughly 50/50 maintenance and proactive work, and the role feels like "just another team member" rather than an outside presence. The difference is that they can commit sustained time to problems that volunteers can't — the deep refactors, the 6-month projects, the work that's been stuck because nobody has bandwidth.

## Why not a flexible contractor pool instead of long-term maintainers?

Context and trust take time to build. The maintenance problems we heard about in team lead interviews (review backlogs, cross-team blocking, complex refactors that need months of sustained attention) require sustained presence, not project-scoped interventions. Contractors for scoped work is a valid model, but it's a different program solving a different problem.

## How will we find the people for the grants team?

That is a challenge. However, the grants team is expected to be a rewarding activity, as it gives team members the opportunity to support one another.

## What if a Maintainer in Residence underperforms?

Performance management is the Foundation's responsibility, not the Project's. The Project treats funded maintainers the same as any team member: Code of Conduct enforcement, team membership decisions, and the normal expectations that come with being on a team. The lines are clear: the Project evaluates candidates going in; the Foundation manages the relationship after.

## What about people who only want to work part time?

The RFMF targets long-term, sustained maintainers, the kind of commitment that's hard to do part time. For contributors who want lighter-touch support, the LC's Project Grants Program ([RFC 3919], $1,500/month) is designed for exactly that. The two programs are complementary: grants support a broad base of contributors; the RFMF funds deep, sustained maintenance work.

## What does this RFC deliberately not specify?

This RFC defines how the Project and Foundation work together to select and manage full-time funded maintainers. It deliberately does not specify how much funding the RFMF has, where that funding comes from, or how funders are solicited. It also leaves operational details to the Foundation: compensation levels, detailed contract terms, part-time vs. full-time arrangements, evaluation criteria specifics, and reporting templates. The broad shape described here is a recommendation, subject to modification over time as the program learns what works.

## What happens if we don't do this?

The Foundation will still operate its fund, but without structured Project input on who to hire or where to focus. There is more risk of misaligned funding, with money going to visible features rather than the invisible maintenance work that keeps Rust healthy. Teams continue to be precarious and isolated, and the Project misses the chance to build a coordination layer that connects willing funders to the work that needs doing.

# Prior art
[prior-art]: #prior-art

## Python Software Foundation: lessons from a mature program

The PSF started its Developer in Residence program in 2021. After nearly five years, it now funds multiple maintainers, each sponsored by a specific company (Meta, Bloomberg, Alpha-Omega, Vercel, among others). Contracts are for 12 months, renewable based on continued sponsor funding. Maintainers are employees or contractors of the PSF, reporting to both the Executive Director and the Steering Council.

The program's evolution taught us several lessons we've incorporated into this RFC. First, pure maintenance work becomes draining over time. The first Developer in Residence started doing only reviews, backports, and CI, and found that after a year or two, "there's not much joy in that." Allowing feature work alongside maintenance "made all the difference." We've reflected this in the RFMF design by recommending open-ended maintenance roles rather than prescribing a rigid split.

Second, sponsors attach to people, not positions. In practice, a sponsor funding a position filled by a particular person will want to continue sponsoring that person specifically if they're happy with the work, rather than funding an abstract role. This has implications for how the Foundation thinks about sponsor relationships: sponsors care about outcomes and the people producing them.

Third, different sponsors want very different levels of engagement. Some are hands-off; others want detailed quarterly reports and input on how maintainers spend their time. The Foundation as an intermediary is valuable here. It buffers the relationship between sponsors and maintainers, so that maintainers aren't managing sponsor expectations directly.

## Django Fellowship: weekly reports and community-focused maintenance

The Django Fellowship program has been running since 2014, predating the PSF program and providing the longest track record of any comparable effort. Fellows are contractors (not employees), expected to commit at least 20 hours per week, with compensation explicitly described as "not competitive with full-time salaries in big cities." The position is ongoing until the Fellow chooses to step down.

Fellows post weekly reports to the django-developers mailing list, a more frequent cadence than the PSF's approach. The work is more narrowly focused on "housekeeping and community support": monitoring security email, fixing release blockers, reviewing pull requests, and mentoring new contributors. The Django model demonstrates that a maintenance-focused role can work long-term even at lower compensation, but also suggests that the pool of people willing to accept those terms is limited.

## Zig Software Foundation: lean and independent

The ZSF takes a simpler approach: core team members bill hours directly to the foundation. As a 501(c)(3) non-profit founded in 2020, 92% of its spending goes directly to paying contributors, with minimal administrative overhead. It has no big tech companies on its board, an explicit design choice to maintain independence.

The ZSF model is leaner and more informal than PSF or Django, but also smaller in scale and more dependent on individual large donations. It demonstrates that low-overhead models are possible, but the approach may not scale to the number of maintainers Rust needs.

## TC's Project Grants Program: the committee model we're building on

The Leadership Council's Project Grants Program ([RFC 3919]) establishes a $100K program supporting ~5 contributors at $1,500/month. It charters a Grants team (5 members, LC-appointed, organized as a Launching Pad subteam) to select recipients and oversee the program. The RFC explicitly positions itself as "distinct from, but complementary to" the RFMF: grants are smaller-scale, flexible, Project-controlled support, while the RFMF targets larger-scale, sustained maintenance.

We build on the Grants team structure directly. Rather than creating a parallel committee with overlapping membership and a similar mandate, the Maintainer in Residence vetting process uses the same Grants team with additional responsibilities. This gives us selection infrastructure and an LC appointment process that already exists, and avoids fragmenting the Project's attention across multiple bodies.

# Unresolved questions
[unresolved-questions]: #unresolved-questions

None.

# Future possibilities
[future-possibilities]: #future-possibilities

## Extending the vetting service to other funding organizations

The clearest message from our team lead interviews was that the most effective way to help teams is to add full-time, long-term maintainers. Short-term grants and scoped contracts have their place, but the problems teams described — review backlogs, cross-cutting refactors, carrying context across a complex codebase — require sustained presence. We encourage any organization looking to fund Rust maintenance to direct funding toward long-term Maintainer in Residence positions.

This RFC defines the interface between the Rust Project and the RFMF specifically, but nothing about the process is inherently RFMF-specific. The Grants team's core service — assessing where full-time maintainers would have the most impact, evaluating candidates, and returning a prioritized recommendation — could be offered to other funding organizations that want to hire Maintainers in Residence. The value proposition is the same regardless of who's paying: the Project has visibility into which teams are struggling and which candidates have the trust and context to be effective, and funding organizations benefit from that assessment rather than making hiring decisions without it.
