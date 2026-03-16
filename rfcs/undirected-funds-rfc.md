- Feature Name: `rust_maintainer_fund`
- Start Date: 2026-02-23
- RFC PR: [rust-lang/rfcs#0000](https://github.com/rust-lang/rfcs/pull/0000)

# Summary
[summary]: #summary

This RFC defines the relationship between the Rust Foundation Maintainer Fund (RFMF) and the open-source Rust project. The RFMF is a dedicated fund used to support Rust maintenance: open-ended, multiplicative work that improves Rust and its codebase and makes it more accessible.

The Leadership Council has a Project Priorities budget, which is used to fund various initiatives, such as travel grants or program management. RFMF funds will be directed to this budget, but they will be earmarked for maintainer sponsorship. That means that they can be used only for activities that directly support Rust Project maintainers, which might include the program management program or the Project Grants Program ([RFC 3919]), which provides modest stipends to recognize and support existing contributors. We propose a new funding program for supporting maintainers described below, which should be the primary target of these earmarked funds.

This RFC adds a new program: Maintainers in Residence (MiR). Maintainers in Residence have dedicated time to focus on some part of the Rust project. Their time is split between priorities guided by the teams they are supporting and priorities of their own choosing within the project.

Selecting Maintainers in Residence is a collaboration between the Foundation and a "Funding team" appointed by the Leadership Council. This Funding team will weigh the set of applications against the project's needs and priorities.

The Funding team is additionally charged with ensuring the program's overall success. When sponsors contribute undirected funding, they are investing in the Rust project as a whole — and the project should meet them in good faith. Project teams receiving support from the program are expected to help the Funding team manage sponsor relations, e.g., by meeting with sponsors or providing other reasonable sponsor benefits.

[RFC 3919]: https://github.com/rust-lang/rfcs/pull/3919

# Motivation
[motivation]: #motivation

The Rust Foundation is establishing a Maintainer Fund to collect sponsorships and provide long-term funding for Rust maintenance. Funds raised through the RFMF are earmarked to fund Rust maintainers under the supervision of the Leadership Council. The Leadership Council commissioned this RFC to recommend how those funds should be used.

Our primary recommendation is that these funds should be used to hire maintainers — called "Maintainers in Residence" — on a full-time or substantial part-time basis, though the Council retains flexibility to deploy funds in other forms such as project grants.

## Why sustained maintainers in residence?

In preparing this recommendation, we interviewed team leads across the Project. The message was clear: *"what's needed is people with the focus to drive longer-scale projects."* Volunteer maintenance keeps the lights on, but larger-scale work — clearing review backlogs, driving cross-cutting refactors, carrying context across a complex codebase — stalls because nobody has the sustained focus to push it through. As one (volunteer) team lead said, *"All the time that reviewers have goes into reviewing, triaging, and so on, and then the interesting longer-term projects just fall under the table."*

The rust-analyzer experience shows what full-time presence makes possible, and what happens when it disappears:

* When a funded reviewer was working on r-a, the PR backlog stayed around 10. After that person changed jobs, it climbed to over 110: *"solving the review problem definitely requires money I think, there's no big question there."*
* Short-term grants help but aren't enough. The Clippy team received Foundation grants that let *"one person work almost full time on Clippy, but it was only for 6 months — it was hard to make long-term plans."*

The problems teams describe require sustained, long-term presence.

## What kind of sponsors do we expect

We expect three kinds of support.

First, small-dollar donations from individuals and organizations that value Rust and want to support its long-term health without any particular expectations. The Foundation will help get the word out via funding drives and PR campaigns.

Second, when the Foundation takes in directed funding towards a particular goal, best practice will be to direct a percentage of that work into the RFMF, providing another revenue stream for maintenance work. (See the [Future Possibilities](#future-possibilities) section for more discussion in this direction.)

The third category is companies that employ developers or contributors working full-time to improve Rust. These companies are invested in Rust development, but their contributors' work still needs to be reviewed and landed by experienced maintainers. The incentive structures at most companies don't reward "general maintenance" like reviewing other people's PRs, mentoring newcomers, fixing regressions, and driving cross-cutting refactors. These activities don't advance any single company's goals, so they're hard to justify in a performance review and vulnerable to restructuring when priorities shift. Sponsoring the maintainer fund is a way for these companies to ensure the maintenance layer their contributors depend on stays healthy.


## Why would companies sponsor the fund

For companies that depend on Rust, what matters most is knowing that the daily work of the project continues — that good ideas won't wither on the vine for lack of reviewer bandwidth, and that bugs will be fixed promptly, particularly bugs they themselves are hitting. Sponsoring the maintainer fund is a direct investment in that capacity.

For the fund to be sustainable, sponsors also need to be able to report the impact of their contributions. This means the project needs to treat demonstrating impact as a whole-project responsibility, not something that falls on Maintainers in Residence alone. See [What sponsors get][] for concrete details on what we envision.

## Why the Project should drive the selection

Much of the work that keeps Rust healthy is not obvious from the outside. Some teams don't directly deliver user-facing features at all: moderation, infrastructure, release. Other critical work is cross-cutting — clearing review backlogs, driving CI improvements, carrying context across a complex codebase. Knowing where a single dedicated person would have the most leverage requires visibility into which teams are struggling and where dependencies are blocking.

Part of the value proposition for sponsors is that they don't have to learn the intimate details of Rust project structure — they can delegate that to the Project. This is why we recommend that the Funding team (composed of active project members selected by the Leadership Council) drive the selection of who to award with a maintainer contract.

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

The RFMF collects sponsorships from companies and individuals. Funds support project grants, project management, and the flagship program: Maintainers in Residence — experienced, self-directed maintainers who do the work that keeps Rust healthy. They participate in team discussions, review PRs, mentor newcomers, and work on what the team needs.

## Design axioms

### The RFMF is a collaboration between the Project and the Foundation

Neither the Foundation nor the Project can operate the RFMF on their own. The Foundation has a bank account, legal entity, and operational capacity, the Project has knowledge of team health and needs. The Foundation is the incoming channel by which most sponsors arrive, but the Project governs the codebase that sponsors want to support. This RFC proposes that both project members (the Funding team) and Foundation staff jointly make major decisions. This is a partnership, not a handoff.

### The Funding team owns the program's success, but they can't do it alone

Together with Foundation staff, the Funding team owns sponsor relations and program success. As the team that selects maintainers and understands project needs, they're best positioned to communicate with sponsors about outcomes and priorities. However, they need support from the broader project — team leads providing updates, maintainers participating in sponsor meetings, and project infrastructure for reporting.

Sponsor engagement does not imply that any technical decisions (RFC approvals, PR reviews, design choices) should be made differently than they would be otherwise.

### Maintainers are team members

Maintainer in Residence candidates must already be members of the relevant Rust team(s) with the permissions needed for the work — reviewing PRs, championing goals, and performing actions limited to official team members. This is a hard requirement, not just an expectation. Funded maintainers are not a separate class of contributor — they're existing team members who can now commit sustained time.

### Not one size fits all

The RFMF doesn't try to be the sole channel for funding Rust maintenance. The Maintainer in Residence program fills a specific role: allowing project teams to select and direct maintainers toward the areas they identify as most critical. Other structures — the proposed Project Goals Funding program for directed grants (see [Future possibilities][]), the Project Grants Program for contributor stipends, the Rust-Analyzer Open Collective, the proposed RustNL Maintainer Fund, company employment — serve complementary roles.

## What sponsors get
[what-sponsors-get]: #what-sponsors-get

RFMF sponsors contribute to a general fund and don't direct where the money goes or who gets hired. Every contribution helps fund the sustained maintenance that keeps Rust healthy. All sponsors receive public recognition and visibility into how funds are being used through regular public reports.

The Foundation should establish sponsorship tiers to encourage larger contributions and year-over-year commitment, as sustained sponsorship permits more stability for the program. The specific tiers are best determined over time by the Foundation and Funding team, but they could include benefits like the following:

* **Sponsor meetings.** The Foundation builds a community of sponsoring organizations that meets with project leadership (Leadership Council, team leads) and Maintainers in Residence a few times a year to discuss project direction, sponsor experiences, and pain points. Project leadership gains insight into the needs of major Rust users; sponsors get visibility into the roadmap and the opportunity to hear from other Rust-adopting companies.
* **Impact reporting.** Regular reports on what funded maintainers are working on, progress on Project Goals, and how the program is contributing to Rust's health. These reports are prepared with help from the program management team and made publicly available.
* **Best-effort attention.** Sponsors can reach out to the Foundation or project contacts about PRs or bugs that need attention. There is no SLA or guarantee — any maintainer would bump a bug report from an active user, and sponsors can reasonably expect the same consideration.

These are reasonable expectations that don't compromise the Project's independence — they represent the kind of engagement any healthy open-source project should provide to its supporters.

*What sponsors do not get:* the ability to unilaterally direct a maintainer's work, pick who gets hired, pick who gets added to project teams, bypass project processes, or influence technical decisions.

## Selection process is driven by a team within the project, supported by Foundation staff

When funding is available, the Funding team and Foundation put out an open call for applications. The Funding team and Foundation staff review applications, consider the project's needs, and then the Foundation makes offers to the strongest candidates.

## The Funding team owns the project's long-term success and interfaces with maintainers-in-residence

The Funding team owns the program's overall success. They keep up with teams to understand where support is needed and how well the program is working; they can adjust aspects of the program to make it work better over time.

If there are concerns about a MiR, they can be raised to the funding team. The team will gather context and work with the Foundation manager to resolve the concern. Typically this means a conversation that brings about a change in behavior. In extreme cases, this might include performance management options like terminating a contract or opting not to renew.

*Unresolved question:* We are describing the Funding team as if they are a distinct team. As described in the [Unresolved questions][], the Leadership Council may opt to instead grow the scope of an existing team like the Grants team.

## What Maintainers in Residence do

Maintainers in Residence split their time between team priorities and individual priorities of their own choosing within their area of focus. The exact balance varies depending on the individual, their experience, and the needs of the team — the important thing is that both team-directed and self-directed work are expected. This is about "team-directed vs. self-directed," not "maintenance vs. features." The PSF's experience after nearly five years confirms that focusing purely on team-directed needs and multiplicative maintenance can be very draining; giving time for self-directed projects "made all the difference" in satisfaction.

# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

## The Funding team

The Funding team's role is to keep a pulse on the project and work with the Foundation to select which maintainers to hire. Its core responsibilities are:

1. **Staying in regular contact with teams** — meeting regularly with team leads and members to understand their needs, health, and where support would have the most impact.
2. **Connecting teams to available resources** — even outside MiR hiring. This might mean redirecting an existing maintainer to help with a situation, connecting a team lead to the Foundation, or surfacing resources a team didn't know existed.
3. **Working with the Foundation to select MiR candidates** — when positions become available, evaluating applicants and selecting candidates who'll have the most overall impact based on project needs.
4. **Collecting feedback on how well the program and the MiRs are working** — as the team responsible for selecting which maintainers to hire, the Funding team is also the team responsible for fielding feedback on how well those decisions work out and making adjustments as needed.

The Foundation supports the Funding team with logistics. The Foundation issues contracts or manages employment. They provide managerial support to convey feedback.

We expect that initially this managerial work can be managed by existing Foundation staff. If the program grows to a large number of MiR, however, we recommend that the Leadership Council use some portion of the RFMF funds to hire a dedicated manager who would work closely with the Funding team (see [Who manages Maintainers in Residence after they're hired?][who-manages-mirs]).

Beyond individual hiring decisions, the Funding team has ownership of the program's long-term health: apportioning available funds across positions, ensuring that funded work gets reported on, demonstrating return on investment to sponsors, and sustaining and growing the program over time. The RFC specifies the inputs and constraints for these decisions — project needs, team health, sponsor priorities, candidate qualifications — but delegates the decision process itself to the team, which is expected to operate transparently and document how it makes decisions.

## Application and vetting process

The process of contracting a new Maintainer in Residence begins with an open call for applications. Any member of a Rust team or person to whom team membership has been offered can apply — broad applications help surface needs and candidates the Funding team might not have identified on its own.

Applicants provide (1) their background and experience — both within the Rust project and professionally; (2) their availability (full-time, part-time, etc); and (3) a high-level description of the kind of work they would like to do. This description can be quite general (e.g., "maintain rustfmt") but could also be specific (e.g., "split project `foo` into multiple independent libraries `bar` and `baz`").

The Funding team prioritizes applications based on:

1. conversations with team leads and team members to assess what support is most urgently needed;
2. the applicant's history with the project;
3. any specific work that was proposed in the application;
4. the applicant's availability and whether it suffices for the tasks they expect to perform;
5. the results of interviews or conversations with the applicant; and
6. any history of interpersonal or Code-of-Conduct issues known to the moderation team.

The Funding team works with the Foundation to select from the applicant pool and to extend offers. The Funding team is looking for maintainers that have technical depth in the relevant area, community standing and trust within the Project, and sustained work orientation (a track record that suggests they'll thrive in a role focused on reviews, mentorship, unblocking, and the kind of long-term technical work that requires deep context).


## Contract terms and renewal

The precise terms of the arrangement are not defined by this RFC. The arrangement is likely to begin as year-long contracts but may change to other durations, regular employment, or vary by locale. The important points are: it is a **substantial commitment** (full-time or significant part-time), and it is expected to **continue as long as both sides are satisfied and funding is available**. Some areas may not require a full person's time; it is fine to have one person cover two areas, or two people each contribute part-time to a single area, so long as there is enough concentrated time to build and maintain deep context.

Compensation should be a flat rate within a small number of bands (e.g., junior and senior), rather than individually negotiated. Flat rates keep the program simple and avoid the perception that some maintainers are valued more than others for equivalent work. The compensation structure is publicly advertised as part of the call for applications. The Foundation determines the specific rates and may adjust them over time as the program learns what works and what's needed to attract strong candidates.

Renewal of contracts is expected but not guaranteed:

* There may not be adequate funds available to continue the existing maintainer contracts.
* The Funding team may feel that there are urgent unmet needs within the project that prompt a change in maintainer (but this is in tension with the primary goal of this RFC of providing long-term, funded maintenance; see below).
* The maintainer may not be doing an adequate job (though this scenario is typically managed separately; see performance management below).

Deciding not to renew a well-performing maintainer in order to fund a different area should not be done lightly. Sustained presence is the core value proposition of the program — startup overhead is real, context takes time to build, and the problems this program targets require continuity. The Funding team should strive to maintain existing maintainers and grow the program to meet new needs rather than redirecting existing positions. Given limited funding, the Funding team can also encourage existing maintainers to pick up work in new areas rather than replacing them.

In advance of contract renewal, the Foundation will consult with the Funding team. The Funding team will assess the needs of the project and decide whether a change should be made. If they do decide to change things, they will issue a new call for applications. If desired, the current maintainer may re-apply.

## Maintainer in Residence expectations

Maintainers in Residence are expected to spend 100% of their funded time working to improve the Rust project. That funded time can be split between:

* **Team priorities** — items that are prioritized by the team(s) that the maintainer was specifically hired to contribute to. This includes reviews, mentoring, bug-fixing, triage, and larger development work like refactors or subsystem rewrites.
* **Self-selected items** — work of the individual's choosing.

Experience with the Python Developer-in-Residence program suggests that for long-term satisfaction, it's important that maintainers be given time to pursue self-selected projects. We've also seen over time that maintainers often develop good instincts for what would generally benefit Rust, and thus self-selected "passion projects" can turn into some of Rust's most impactful features.

The split between team priorities and self-selected work will depend on the individual. The Funding team should monitor and make sure that team priorities are being adequately served, while also ensuring that MiRs have the opportunity to pursue self-selected work. If both cannot be done, that likely indicates the need for another MiR in that area.

Maintainers in Residence are also expected to:

* resolve time-critical issues such as urgent bugs;
* champion Project Goals supported by their respective teams, even if they themselves might not have championed that goal as an individual;
* work with the Project to ensure their work gets regularly reported on;
* remain a member of the Project and relevant teams, in good standing.

## Responding to sponsor requests

Sponsors can reach out to the Foundation or project contacts about PRs or bugs that need attention. This is best effort, not an SLA — any maintainer would bump a bug report from an active user, and sponsors can reasonably expect the same consideration.

Requests that go beyond this — "develop this feature" or "devote sustained time to our priority" — are outside the scope of this relationship. (The [Future possibilities][] section describes a Project Goal Funding program that could support sponsors seeking that level of direction in the future.) The Foundation manages sponsor expectations and serves as a buffer so that maintainers aren't negotiating these boundaries directly.

## Reporting and impact visibility


While MiR are expected to help collect data for reporting, they will be supported by the project, and the overall reporting expectations should not be substantively more onerous than for volunteer contributors. The point is to reduce burden, not add it.

Examples of project support include:

* The program management team will prepare an initial draft by examining GitHub activity (PR reviews, etc.) and via updates on Project Goals championed by the maintainer.
* The Content team will interview maintainers and highlight their work.

Program managers collect progress updates from goal owners (funded or not) on a regular cadence and prepare summaries. For funded maintainers, these summaries serve double duty: they give the Project visibility into goal progress, and the Foundation can use them to prepare sponsor-facing reports.

## Performance management

The Foundation staff and the Funding team will monitor the maintainer's work and periodically solicit feedback from contributors and other team members. The moderation team is encouraged to inform the Funding team and/or Foundation about any reported issues relevant to a MiR's conduct.

If a maintainer is not performing well, Foundation staff are expected to provide constructive feedback. If performance does not improve, the Foundation may decline to renew the contract or, in serious cases, terminate it early. The Foundation is responsible for the operational side of these decisions (contract changes, termination).

As the program grows, we may wish to transition this role from a responsibility of the Foundation staff to a dedicated manager working within the project. See [the FAQ on this topic.][who-manages-mirs]

Separately, Code of Conduct violations that result in removal from the Project immediately terminate the contract. Team membership is a hard requirement for the role; a maintainer who is no longer a project member cannot continue as a Maintainer in Residence.

The Project does not decide whether a contract gets renewed; it provides input.

# Frequently asked questions
[faq]: #faq

## What does it look like to have a Maintainer in Residence on my team?

In one sense, the same as having any other team member. They show up in reviews, participate in design discussions, mentor newcomers, and work on what the team needs. The PSF's experience after nearly five years is instructive: the Developer in Residence does roughly 50/50 maintenance and proactive work, and the role feels like "just another team member" rather than an outside presence.

But there is an important difference beyond just having more time. Most team members are volunteers, and teams can't ask volunteers to take on specific tasks — they can only hope someone steps up. A Maintainer in Residence, by contrast, has dedicated part of their time to team priorities. The team should feel free to ask a MiR to take on high-priority work that nobody else can tackle — championing a goal, driving a critical refactor, clearing a review backlog — so long as it fits within that team-priorities capacity. This is a resource that teams have never had before, and it changes the dynamic from "hoping someone volunteers" to "directing sustained effort where it's needed most."

While MiRs should help teams with their needs, they also have a right to reserve time for their own priorities. MiR can feel free to decline to work on team priorities past a certain point. The Funding team will help to negotiate this balance as needed.

## Why not a flexible contractor pool instead of long-term maintainers?

Context and trust take time to build. The maintenance problems we heard about in team lead interviews (review backlogs, cross-team blocking, complex refactors that need months of sustained attention) require sustained presence, not project-scoped interventions. Contractors for scoped work is a valid model, but it's a different program solving a different problem.

## How will we find the people for the Funding team?

The same way we find people for any other team. Funding team work is expected to be rewarding, as it gives team members the opportunity to understand the project holistically and support one another.

## Who manages Maintainers in Residence after they're hired?
[who-manages-mirs]: #who-manages-maintainers-in-residence-after-theyre-hired

The Funding team's role ends with the recommendation. Someone needs to synthesize feedback from the Project and make the call on performance. There are two main options:

**Foundation manages (current RFC position).** Management and performance feedback are skills, and the Foundation has professional staff experienced in them. This shouldn't be a heavy lift early on — we're selecting experienced, self-directed maintainers who are unlikely to have significant performance issues. The Foundation gathers input from the Project (team leads, collaborators) and synthesizes it.

**Project manages.** The Project has deeper technical context to evaluate whether work is landing well. But Project-side management means either a volunteer committee handles it (likely unskilled at management, outside the Funding team's competency) or a dedicated person is hired for it (high overhead relative to the program size, especially early on).

In practice, we expect this to be a phased approach. While the program has relatively few maintainers, the Foundation provides management skill and the Funding team provides feedback as an input. As the program grows, a dedicated support role may emerge — someone who meets with MiRs regularly, helps them build a portfolio of their work, and serves as the point of contact when teams have concerns. Whether that role lives within the Foundation, the Project, or somewhere in between is a question that becomes more important at scale and can be revisited as the program learns what it needs.

## What if a Maintainer in Residence underperforms?

See the ["Who manages MiR"][who-manages-mirs] question.

## What about people who only want to work part time?

Maintainers in Residence can work substantial part-time — the key requirement is enough concentrated time to build and maintain deep context, not necessarily a 40-hour week. Some areas may not need a full person's time, and it's fine to have one person cover two areas or two people each contribute part-time to a single area. For contributors who want lighter-touch support, the LC's Project Grants Program ([RFC 3919]) is designed for exactly that. The two programs are complementary: grants support a broad base of contributors; the RFMF funds sustained maintenance work from people with deep context.

## What about sponsors who want to pay for a particular item to get done?

That's outside the scope of the RFMF, which is undirected funding — sponsors contribute to a general fund and the Leadership Council decides how to deploy it. A companion effort, the proposed Project Goals Funding program (see [Future possibilities][]), is designed for exactly this: sponsors direct funding at specific Project Goals, and the Foundation issues grants to advance that work. Sponsors seeking that level of direction should look there rather than the RFMF.

## Why are RFMF funds earmarked for maintainers?

Sponsors contributing to the RFMF want to know their money is going directly to fund maintainers. Earmarking gives the fund a clear value proposition: every dollar goes to paying people who maintain Rust. Without earmarking, the Leadership Council could use RFMF funds for any purpose — travel grants, event sponsorship, infrastructure — all valuable, but harder to explain to a company evaluating its return on investment. Since money is fungible, earmarking RFMF funds for maintainers also frees up other budget for those other purposes.

The earmark is broad: Maintainers in Residence, project grants, and the program management overhead needed to support them. The Leadership Council determines the specific form. This gives the Council real flexibility while keeping the fund's purpose legible to sponsors.

## What does this RFC deliberately not specify?

This RFC defines how the RFMF collects sponsorships, the benefits sponsors receive, and how the Project and Foundation work together to select and manage Maintainers in Residence. It deliberately does not specify how much funding the RFMF has, specific sponsorship tier structures, or detailed solicitation strategy. It also leaves operational details to the Foundation: compensation levels, detailed contract terms, evaluation criteria specifics, and reporting templates. RFMF funds are earmarked for funding maintainers, but the Leadership Council determines how much of those funds to use for MiR vs Project Grants vs other programs. The broad shape described here is a recommendation, subject to modification over time as the program learns what works.

## What happens if we don't do this?

The Foundation will still operate its fund, but without structured Project input on who to hire or where to focus, and without a clear earmark ensuring funds go to maintainers. There is more risk of misaligned funding, with money going to visible features rather than the invisible maintenance work that keeps Rust healthy. Teams continue to be precarious and isolated, and the Project misses the chance to build a coordination layer that connects willing sponsors to the work that needs doing.

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

The program originally required a minimum of 20 hours per week, with compensation described as "not competitive with full-time salaries in big cities." Over time it has evolved: the program now has three Fellows, some working full-time, with compensation adjusted annually. The Django model demonstrates that a maintenance-focused role can work long-term, and that programs naturally evolve toward more hours and more competitive compensation as they prove their value.

## Zig Software Foundation: lean and independent

The ZSF takes a simpler approach: core team members bill hours directly to the foundation. As a 501(c)(3) non-profit founded in 2020, 92% of its spending goes directly to paying contributors, with minimal administrative overhead. It has no big tech companies on its board, an explicit design choice to maintain independence.

The ZSF model is leaner and more informal than PSF or Django, but also smaller in scale and more dependent on individual large donations. It demonstrates that low-overhead models are possible, but the approach may not scale to the number of maintainers Rust needs.

## Scala Center: pool-funded with sponsor engagement

The Scala Center, housed at EPFL, takes a pool-funded approach that contrasts with the PSF's per-sponsor-per-position model. Corporate sponsors contribute to a general fund at tiered levels and send representatives to quarterly Advisory Board meetings. The Advisory Board makes non-binding recommendations on priorities; the Center's leadership decides on execution and hiring. Sponsors influence direction through discussion but don't direct specific positions or hires.

Two aspects of the Scala Center model have been particularly influential on this RFC. First, the sponsor meeting structure: sponsors meet regularly with maintainers and with each other, and these meetings have been described as a "big win" for selling the program internally. Having sponsor representatives commit to attend regular meetings makes the program legible to upper management. Second, sponsors often value hearing from their peers — other organizations using the language — as much as from the project itself. Both of these insights shaped the RFMF's sponsor engagement design.

The Scala Center employs engineers directly as university employees, which provides stability but depends on university infrastructure. That structural detail doesn't transfer to Rust, but the pool-funding model and sponsor engagement approach do. The Scala Center demonstrates that sponsors will contribute to a general fund without earmarking, provided they get meaningful engagement in return.

## Project Grants Program: a related committee model

The Project Grants Program ([RFC 3919]) proposes a program supporting a handful of contributors with modest monthly stipends. It charters a Grants team (5 members, LC-appointed, organized as a Launching Pad subteam) to select recipients and oversee the program. The RFC explicitly positions itself as "distinct from, but complementary to" the RFMF: grants are smaller-scale, flexible, Project-controlled support, while the RFMF targets larger-scale, sustained maintenance.

The Grants team's charter overlaps significantly with the Funding team charter we define here — both involve assessing project needs and selecting candidates. The Leadership Council may choose to extend the Grants team with the Funding team's responsibilities rather than creating a separate body, which would avoid fragmenting the Project's attention across multiple committees with overlapping mandates.

# Unresolved questions
[unresolved-questions]: #unresolved-questions

## Organizational form of the Funding team
[funding-team-org]: #organizational-form-of-the-funding-team

This RFC defines the Funding team's charter — its responsibilities — but leaves the organizational structure to the Leadership Council. There are two main options:

**Extend the Grants team.** The Grants team proposed in [RFC 3919] already has an LC appointment process, selection infrastructure, and conflict-of-interest policies. Extending it avoids fragmenting volunteer attention across overlapping committees.

**Create a new team.** The Funding team's charter is broader than selecting recipients — it includes staying in regular contact with teams, connecting them to resources, and understanding project health holistically. MiR selection is only one part of that mandate. A new team with a broader mandate may be a better fit than extending a team whose focus is choosing grant recipients. There is also a difference in operating cadence: the Grants program has predictable cycles, while the Funding team may need to react promptly when new funding becomes available rather than waiting for the next scheduled round. Current Grants team members may not have signed up for that kind of bandwidth or latency.

We expect the Leadership Council to determine the right organizational form.

# Future possibilities
[future-possibilities]: #future-possibilities

## Extending the vetting service to other funding organizations

This RFC defines the interface between the Rust Project and the RFMF specifically, but nothing about the process is inherently RFMF-specific. The Funding team's core service — assessing where dedicated maintainers would have the most impact, evaluating candidates, and selecting the best candidates — could be offered to other funding organizations that want to hire Maintainers in Residence. The value proposition is the same regardless of who's paying: the Project has visibility into which teams are struggling and which candidates have the trust and context to be effective, and funding organizations benefit from that assessment rather than making hiring decisions without it.

## Recording MiR affiliations

If the Rust Project establishes a mechanism for recording affiliations of team members, Maintainers in Residence could record their RFMF funding as an affiliation. This would make funding relationships visible through the same infrastructure used for employer affiliations.

## Project Goals Funding program

The RFMF provides undirected funding — sponsors contribute to a general fund earmarked to fund Rust maintainers, with the Leadership Council deciding the specific form. There are ongoing plans to propose a Project Goals Funding program that would allow sponsors to direct funding at specific Project Goals. Sponsors would choose goals, roadmaps, or application areas to fund, and the Foundation would issue grants to contributors working on that work. A percentage of directed funding would flow to the Leadership Council's Project Priorities budget, where it can be used to fund maintenance, project management, or other activities. Together, the two programs cover the full spectrum of sponsor needs: undirected funding for those who want to support Rust's overall health, and directed funding for those who want to accelerate specific work.

