- Feature Name: `project_goals_funding`
- Start Date: 2026-02-23
- RFC PR: [rust-lang/rfcs#0000](https://github.com/rust-lang/rfcs/pull/0000)

# Summary
[summary]: #summary

This RFC establishes the Project Goals Funding program, a mechanism for sponsors to fund Rust development by contributing toward technical roadmaps published through the Project Goals program. Sponsors contribute toward specific roadmaps, such as [Just add async](https://rust-lang.github.io/rust-project-goals/2026/flagship-just-add-async.html), [Beyond the `&`](https://rust-lang.github.io/rust-project-goals/2026/roadmap-beyond-the-ampersand.html), or [Constify all the things](https://rust-lang.github.io/rust-project-goals/2026/roadmap-constify-all-the-things.html). The vetting and approval process of the Project Goals program ensures that these roadmaps are aligned with project priorities.

A fixed percentage of every directed contribution flows to a general fund. The Leadership Council determines how that general fund is spent, ensuring that maintainer funding is available for less glamorous tasks and projects that rarely lie on the critical path of user features, such as moderation or the rustup tool.

The remaining directed funds are used to advance the roadmap in whatever ways are most useful. The decisions for how to spend those directed funds are made by the Foundation staff working together with the Goals team and the point-of-contact for the roadmap itself. This could include hiring contractors to do development and sponsoring travel and discussions; for larger roadmaps, it may also include supporting dedicated maintainers to champion and review this specific work.

Dedicated maintainers for a specific roadmap don't have to be contracted through the Foundation. When an existing structure already supports maintainers in the relevant area, such as the Rust-Analyzer Open Collective or the proposed RustNL Maintainer Fund, dedicated maintainer funds are sent there. If no existing structure exists, the Foundation can contract with a dedicated maintainer directly, though in this case the focus is the roadmap and not "whatever the project deems most important".

# Motivation
[motivation]: #motivation

Rust adoption is accelerating. Companies are building safety-critical systems, cloud infrastructure, and operating system components in Rust. Projects like Rust-for-Linux and Canonical's adoption of Rust for system components reflect a growing confidence in the language. With that confidence comes a willingness to invest: companies have budget and want to see Rust succeed in the areas they care about.

But there is no clear path from "we have budget" to "work gets done". A company that needs better async networking support, or better interop with C++, knows the *problem* but not the *solution*. Even when they can articulate what they need, finding the right person to do the work is hard — and finding someone is only half the battle, because that contributor's work still needs to be reviewed and landed by an experienced maintainer. Without that maintainer, contributions sit in a queue.

The Project Goals Funding program aims to close that gap, building on the Project Goals program — which produces project-vetted technical roadmaps that map user-facing problems to concrete engineering work — and the operational capacity of the Rust Foundation to serve as an intermediary between sponsors and maintainers.

## Landing work requires both contributors and maintainers

Open-source development requires two distinct roles, contributors and maintainers. These words are often used interchangeably but we draw a sharp distinction in this RFC:

* The *contributor* is the person who drives the change. They write the code, run the experiments, author the RFC, etc.
* The *maintainer* is the one who reviews the work. They mentor contributors, review and provide feedback on PRs, and ultimately decide which changes to accept. As the people most familiar with the codebase overall, maintainers are also the ones to drive large, cross-cutting refactorings or changes.

While the roles are distinct, the people playing them are often not: maintainers also write PRs and develop new features. But in this case they need the support of *another* maintainer to do the reviews.

## Companies are a natural fit for the contributor role

Many companies already employ full-time Rust contributors, and this is a good thing. Company employees are the ones putting Rust to use directly, giving them first-hand contact with real users and real problems. This makes it natural for them to prioritize work and gives the project confidence that proposed designs meet actual needs. The incentive alignment is straightforward: shipping features and driving technical initiatives is what companies reward.

## But contributors alone leave a gap

Company-funded contributors can drive changes, but their work still needs to be reviewed and landed by experienced maintainers. Much of maintenance work is about generalizing Rust's support in ways that don't directly advance a single company's goals: reviewing other people's PRs, mentoring newcomers, fixing regressions, driving cross-cutting refactors. Companies can and do support this work, but the role is hard to justify in a performance review and vulnerable to restructuring when priorities shift. *"Even those funded don't necessarily get funded for maintenance and keeping the train rolling, some of that is only towards features rather than things which make the whole codebase better,"* as one team lead put it.

Even among maintenance work, there is a spectrum of visibility. Some areas like the compiler have clear value that sponsors can see. Others — moderation, the rustup tool, CI infrastructure — are essential but rarely on anyone's "critical path" of user features. These teams often receive relatively little support and attention, and team leads report feeling adrift: *"By and large I think teams are on their own to solve their own problems. Not how it should be but it's how it is. There isn't an amazing venue or team that is thinking about the project health holistically."*

## Raising maintainer funding is hard for the same reasons

Raising money is much easier if you can articulate the impact of that funding. Some companies will donate money into a general fund, but most would like to have a clear picture of the impact from their donations. When money is pooled together, that impact becomes diffuse, and it's tempting for any individual sponsor to assume that others will cover the gap if they pull out. As one of the PSF's Developer in Residence described it, *"the sponsor wants to see what their money is being spent on ... very quickly that becomes the value prop when they are discussing internally whether to put in the $$ or not."*

This is why the Project Goals Funding program pairs directed funding with a general maintenance fund. Sponsors can direct funding toward specific technical roadmaps published through the Project Goals program — roadmaps that address the problems they care about. A fixed percentage of every directed contribution flows to the general fund, ensuring that less glamorous but essential work gets covered. And the Project helps the Foundation ensure that each roadmap has the right mix of contributors and maintainers to actually deliver.

## Each roadmap has distinct funding needs

The right mix of contributors and maintainers depends on the specific roadmap. In some cases, a company already employs a senior leader who can provide the design guidance and review bandwidth, but contractors are needed to push the implementation work forward — as with a goal like [open namespaces](https://rust-lang.github.io/rust-project-goals/2026/open-namespaces.html), where the design lead is in place but the implementation needs dedicated effort. In other cases, there is a willing contributor but no maintainer with bandwidth to review the work. The Project Goals team and the Foundation work together to assess each roadmap's needs and direct funding accordingly.

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

The Project Goals Funding program allows sponsors to contribute toward specific technical roadmaps published through the Project Goals program, with a fixed percentage of every directed contribution flowing to a general fund directed by the Leadership Council.

## Design axioms

### Sponsors influence the when, not the what

Sponsor funding doesn't change any of the Project's decision-making processes. No amount of money makes an RFC get accepted or a feature get prioritized that the Project wouldn't pursue on its own. Sponsors accelerate work that's already on the roadmap.

### Directed funding sustains general maintenance

Sponsors naturally want to fund work they can see — specific roadmaps, specific features. A fixed percentage of every directed contribution flows to the general fund, ensuring that essential but unglamorous work (moderation, rustup, CI infrastructure) gets covered even when no sponsor would choose to fund it directly.

### Not one size fits all

The Project Goals Funding program doesn't try to be the sole channel for funding Rust maintenance. When it comes to directed funds, they can be used in a way most appropriate to the situation, including helping to support maintainers working elsewhere.

### The Project helps maintainers demonstrate their impact

The Project provides scaffolding — goals, program management, reporting infrastructure — so maintainers can focus on the work while sponsors get visibility into outcomes.

## Directed funding

### Connecting sponsors to the work they care about

Roadmaps serve as the menu for directed funding. The Project Goals program is already working to organize goals into coherent technical roadmaps focused on end-user outcomes — such as [Just Add Async](https://rust-lang.github.io/rust-project-goals/2026/flagship-just-add-async.html), [Beyond the `&`](https://rust-lang.github.io/rust-project-goals/2026/roadmap-beyond-the-ampersand.html), and [Constify all the things](https://rust-lang.github.io/rust-project-goals/2026/roadmap-constify-all-the-things.html). Most pain points that sponsors encounter have been encountered before, and there is often ongoing work to address them. Part of the program's job is to connect sponsors to the people in the Project who are already doing the work they care about. If no existing roadmap fits a sponsor's interests, the Foundation and Goals team can work with them to develop one (see [Sponsor requests outside existing roadmaps][] below).

### Every directed contribution sustains general maintenance

A fixed percentage of every directed contribution flows to a general fund. The Leadership Council determines how that general fund is spent, ensuring that essential but unglamorous maintenance work is sustained. The remaining directed funds are used to advance the roadmap in whatever ways are most useful. The Foundation works with the Goals team and the roadmap's point-of-contact to assess what each roadmap needs — whether that means hiring contributors, supporting maintainers who work elsewhere, sponsoring travel and coordination, or contracting dedicated maintainers. Sponsors receive updates on roadmap progress through the Project Goals program, which collects progress updates on a regular cadence and prepares summaries that serve both the Project and sponsor-facing reporting needs.

# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

## Directed funding mechanics

### A fixed percentage of directed funds go towards undirected work

A fixed percentage of every directed contribution flows to a general fund directed by the Leadership Council. This ensures that directed funding — which naturally gravitates toward visible, high-impact areas — also sustains the essential but unglamorous maintenance work that no individual sponsor would choose to fund. The exact percentage is for the Foundation to determine; for reference, universities typically divert ~30% of grant funding to indirect costs.

### How directed funds are spent

The remaining directed funds are used to advance the roadmap in whatever ways are most useful. The Foundation works with the Goals team and the roadmap's point-of-contact to assess what each roadmap needs. The right mix depends on the situation:

* **Contributors and contractors** to drive implementation work — writing code, running experiments, authoring RFCs.
* **Supporting maintainers who work elsewhere.** When a roadmap involves an area where maintainers are already supported through another structure — the Rust-Analyzer Open Collective, the proposed RustNL Maintainer Fund, or a company that employs the relevant reviewer — directed funds can flow there rather than through the Foundation.
* **Travel, discussions, and coordination** to bring the right people together for design work and decision-making.
* **Dedicated maintainers** contracted through the Foundation for larger roadmaps that need sustained review and design guidance in a specific area.

### Checking for maintainer bandwidth

Before directing funding toward a roadmap, the Goals team checks whether the relevant teams have enough maintainer capacity to absorb new contributions. A roadmap that rests on types team work isn't going to move if nobody on the types team has bandwidth to review. If maintainer capacity is insufficient, the Goals team and Foundation work together to address the gap — whether by directing a portion of the funding toward maintainer support, adjusting the scope, or sequencing the work differently.

### Sponsor requests outside existing roadmaps

When a potential sponsor has needs not covered by current roadmaps, the Foundation puts them in touch with the Goals team, who can evaluate whether a new roadmap makes sense. This ensures that sponsor interest can surface priorities the Project hasn't yet organized into a roadmap, while the Project retains control over what gets approved.

## Reporting and impact visibility

Funded work participates in the Project Goals process. If funded contributors champion a goal, they show up in the goal's tracking and reporting. If funded maintainers provide review bandwidth for a goal, that's reflected in the goal's progress updates. The Goals program is the reporting infrastructure.

Program managers collect progress updates from goal owners on a regular cadence and prepare summaries. For directed funding, these summaries cover roadmap progress and serve double duty: they give the Project visibility into goal progress, and the Foundation can use them to prepare sponsor-facing reports.


# Frequently asked questions
[faq]: #faq

## What is the percentage that flows from directed funding to the general fund?

This RFC deliberately does not specify the exact percentage. The Foundation is in the best position to make that call, balancing the need to sustain general maintenance against the need to make directed funding attractive to sponsors. For reference, universities typically divert ~30% of grant funding to indirect costs, but the right number may be higher or lower depending on how the fund develops. What matters from the Project's perspective is that the mechanism exists and that it is applied consistently.

## What if a sponsor wants to fund an area that isn't on any roadmap?

The Foundation brings the request back to the Project — through the Goals team, relevant teams, or the user research team — and works to find a way to create a roadmap that addresses the sponsor's needs. Sponsors can also develop and propose their own roadmaps, and we strongly encourage that, though it may take some time before the proposal reaches the point where the relevant teams can accept it. The normal Goals vetting process still applies: teams have to agree to the goals in a roadmap before it's approved.

## What if sponsors want more influence than the axioms allow?

The directed funding path gives sponsors a way to fund a specific roadmap, and that's a real form of influence. But sponsors don't pick people, don't direct technical decisions, and don't sit on any selection committees. If that's not enough, the sponsor and the Foundation need to work it out; it's not the Project's problem to solve.

## How does this relate to the LC's Project Grants Program?

The Project Grants Program ([RFC 3919]) supports contributors at a smaller scale ($1,500/month). The two programs are complementary: grants support a broad base of contributors; the Project Goals Funding program connects sponsors to larger-scale roadmap work that needs a mix of contributors, maintainers, and coordination.

[RFC 3919]: https://github.com/rust-lang/rfcs/pull/3919

## What does this RFC deliberately not specify?

This RFC defines how the Project Goals Funding program connects sponsors to Project-vetted roadmaps and how directed funds flow. It deliberately leaves operational details to the Foundation: compensation levels, detailed contract terms, how sponsors are solicited, and reporting templates. How the general fund is spent is determined by the Leadership Council. The broad shape described here is a recommendation, subject to modification over time as the program learns what works.

## What happens if we don't do this?

Companies continue to fund contributors but not maintainers. Contributions sit in review queues. The Project misses the chance to build a coordination layer that connects willing sponsors to the work that needs doing, and the fundraising difficulty persists because there's nothing concrete for sponsors to fund.

# Prior art
[prior-art]: #prior-art

## Python Software Foundation: sponsors attach to people, not positions

The PSF started its Developer in Residence program in 2021. After nearly five years, it now funds multiple maintainers, each sponsored by a specific company (Meta, Bloomberg, Alpha-Omega, Vercel, among others). Contracts are for 12 months, renewable based on continued sponsor funding.

The program's evolution taught us several lessons relevant to directed funding. First, sponsors attach to people, not positions. In practice, a sponsor funding a position filled by a particular person will want to continue sponsoring that person specifically if they're happy with the work, rather than funding an abstract role. This has implications for how we think about directed sponsorship: sponsors care about outcomes and the people producing them, and the program design needs to accommodate that without letting sponsors pick maintainers directly.

Second, different sponsors want very different levels of engagement. Some are hands-off; others want detailed quarterly reports and input on how maintainers spend their time. The Foundation as an intermediary is valuable here. It buffers the relationship between sponsors and maintainers, so that maintainers aren't managing sponsor expectations directly. As one of the PSF's Developer in Residence described it, *"the sponsor wants to see what their money is being spent on ... very quickly that becomes the value prop when they are discussing internally whether to put in the $$ or not."*

## Scala Center: sponsor meetings as a selling point

The Scala Center at EPFL operates as a university unit rather than an independent foundation. It has a simple one-tier corporate sponsorship structure with quarterly meetings between maintainers and sponsor representatives. Sponsors send representatives, generally people on internal support teams, who attend these regular meetings and provide feedback.

The non-obvious lesson from the Scala Center is that these meetings are a selling point, not a cost. Having sponsor representatives commit to attend regular meetings makes it easier to sell the program internally at the sponsor's company, because it becomes something upper management understands and can engage with. Sponsors also appreciate meeting with other adopters and discussing challenges.

# Unresolved questions
[unresolved-questions]: #unresolved-questions

None.

# Future possibilities
[future-possibilities]: #future-possibilities

