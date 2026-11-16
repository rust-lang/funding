# Maintainer in Residence program

The Maintainer in Residence (MiR) program is designed to provide sustainable funding for Rust Project contributors for their maintenance work on the Rust toolchain. It is managed by the Rust Funding team.

Here we document how the program works, how to apply for it, and many other useful information. This documentation extends the description of the MiR program originally defined in [RFC #3931][rfc-3931]. That RFC described the high-level motivation for the program. Here, we keep an up-to-date description of how the program works in practice.

You can find the current list of Maintainers in Residence on the [Rust Website][mir-list]. See [here](#how-to-apply) for how to apply to the program.

[rfc-3931]: https://rust-lang.github.io/rfcs/3931-rfmf-rust-foundation-maintainer-fund.html
[mir-list]: https://rust-lang.org/funding/mir.html

## How the MiR program works

The main goal of the MiR program is to support Rust teams in order to fulfill their maintenance needs, and by that improve the long-term health and sustainability of the Rust Project overall. We do that by providing contracts to individual Rust Project members for maintenance activities, typically scoped to work within a small set of Rust teams and projects.

The Funding team continuously evaluates the maintenance needs of Rust teams. When we notice a situation where a team needs more maintainers, and we can dedicate funds for it, we will try to find a Rust Project member who is available and interested in being a MiR for that team. Ideally, it would be an existing member of the team that we want to support, but that might not always be possible.

If we find a good fit, we will fund that maintainer for their maintenance work for the following 12 months, with the expectation of renewal.

## Expectations of how MiRs operate

There are no strict guidelines on what exactly a MiR should be doing, but we expect that MiRs will allocate some portion of their time towards the priorities of their team. They will perform code reviews, participate in design discussions, mentor newcomers, and work on what the given team needs.

Teams should feel free to ask a MiR to take on high-priority work that nobody else can tackle (championing a goal, driving a critical refactor, clearing a review backlog). However, teams should also bear in mind that a MiR does not have infinite capacity. MiRs can feel free to decline to work on team priorities past a certain point. The MiR manager and Funding team will help to negotiate this balance as needed.

We also encourage MiRs to balance work that "has to be done" (e.g. code reviews) with work that they enjoy doing, to avoid feeling overwhelmed and risking burning out.

Note that MiRs are normal members of their teams and the Rust Project, they do not get any extended privileges by being funded by the Funding team.

### Temporary unavailability

MiRs are not required to ask for vacations or anything like that. However, if they know in advance that they will be unresponsible on GitHub and Zulip for an extended period of time (e.g. >1 week), we encourage them to share their expected (un)availability in the designated private Project [topic][zulip-vacation-topic] on the Rust Zulip.

[zulip-vacation-topic]: https://rust-lang.zulipchat.com/#narrow/channel/546943-all.2Fprivate/topic/Vacation.2Fetc.2E.20announcements/with/640771120

### Reporting

We want to ensure that the great work done by our MiRs is promoted, so that we can find funds to continue running this program in a sustainable way for many years to come.

Each MiR is assigned their manager, one member of the Rust Funding team. The manager performs regular check-ins with the MiR, usually once per month. For the check-in, we generate a scraped list of GitHub and Zulip contributions of the MiR in the recent time period, to help the MiR remember the work that they did recently. We then ask the MiR to provide their own commentary on their work, to give us more context into it.

We summarize those reports in public blog posts published on the [Rust Blog][rust-blog-funding] quarterly.

[rust-blog-funding]: https://blog.rust-lang.org/tags/funding/

## MiR roles

We offer several MiR "roles", which determine how much work/time we expect each MiR to spend on maintaining Rust each month, and thus also the financial reward that they receive for it. We use a flat reward structure to avoid leading reward negotiations with MiRs. We also do not specify the reward per hour, but per month, to provide more flexibility for MiRs.

Currently, we offer the following three roles:
- Full-time MiR, for $10k/month
- Part-time MiR, for $5k/month
- Maintainer grant, for $1-2k/month

The Maintainer grant is designed to be a small-scale support for contributors who can't, or don't want, to work on Rust more than 1-2 days per week. Maintainer grants serve as a continuation of the previous Rust Project Grant program.

We expect MiRs to contribute in a capacity corresponding to their role (i.e. ~40 hours/week for the full-time role and ~20 hours/week for the part-time role).

### Funding arrangement

Right now, we can't offer employment for MiRs, so we only offer contracting and grants:
- Full-time and part-time MiRs sign a contract with the Rust Foundation. Then they send an invoice to the Rust Foundation every month, for a flat amount ($5k or $10k).
- Maintainer grantees sign a simpler grant contract. Then they receive a flat amount every month, without having to send an invoice.

All signed contracts are for 12 months. We want to provide sustainable funding, and generally expect to renew each contract as long as we have funds for it.

In situations where we would not have enough funds to prolong a contract, we will notify the funded maintainer in advance (at least 2-3 months).

## How to apply

To apply for a MiR position, please fill the Rust Funding form. The link to the form can be found [here][funding-form-link], at the Rust Zulip. It is only available to Rust Project members.

[funding-form-link]: https://rust-lang.zulipchat.com/#narrow/channel/546943-all.2Fprivate/topic/t-funding.3A.20Rust.20Funding.20Request.20Form.20-.20Please.20share.21/near/601247464

### Eligibility

The MiR program is currently only available to Rust Project members. Each MiR has to remain in good standing with the Rust Project in order to be eligible for being funded as a MiR. Violations of the Rust [Code of Conduct][coc] that result in the MiR being removed from the Rust Project will lead to a termination of their contract.

Before accepting a new MiR, the Funding team will reach out to the leads of the team(s) which the MiR is designed to support, and also to the Rust moderation team, to find out about any potential issues.

[coc]: https://rust-lang.org/policies/code-of-conduct/

## How do we select MiRs

Usually, we get many more applicants for a MiR role than what we can afford to fund. To avoid arbitrarily picking MiRs from a large set of applicants, we approach this from the other direction, by focusing on team maintenance needs first.

We regularly communicate with Rust teams to determine their "maintenance baseline", i.e. the equivalent of a number of full-time maintainers needed for the team to be healthy and stay on top of the projects that it maintains. We want to ensure that each team has enough people to perform code reviews and refactorings necessary for new features and improvements to land without the tech debt not increasing too much, and without maintainers burning out.

We assign priority to *teams* that are understaffed, to figure out the next best team to be supported with a MiR. Only once we determine such a team, do we then go look at the list of MiR applicants, to try to find the best person to support that team.

The process of selecting individual teams and applicants is mostly performed in private, to avoid giving out false hopes when things change, and to avoid leaking personal details about e.g. the job status of individual people.

The whole Rust Funding team participates in the selection process, and in voting to decide which teams to prioritize, and which MiRs to hire to support a given team. During the selection process, the Funding team will discuss their choices with the team lead(s) that the MiR is designated to support (unless the team lead in question is the MiR candidate themselves).

## Where do we get funds

The main source of funds for the MiR program is the [Rust Foundation Maintainers Fund][rfmf]. It receives donations from both companies and individuals (through GitHub Sponsors) that are interested in helping fund the maintenance and development of Rust.

The Rust Leadership Council also dedicates a part of its Project Priorities budget to RFMF.

[rfmf]: https://github.com/sponsors/rustfoundation
