# Funding team charter

The goal of the Funding team is to improve the overall health and long-term sustainability of the Rust Project and its teams, primarily by financially supporting Project team members for their upstream maintenance work.

Its primary high-level duties are to:
- Communicate with Rust Project teams and maintainers to figure out their funding needs.
- Distribute available funds to financially support Rust Project maintainers.
- Communicate with funders and promote the work of supported maintainers to help find and keep sustainable funding.
- Work transparently and in public as much as possible, unless the discussion cannot be made public due to private details.

The Funding team has to make difficult choices about who to financially support, as often there are several great choices, but not enough funds to support all of them. It should strive to make decisions that will be the best for the overall health of the Rust Project and its teams.

## Scope of the funding

In terms of scope, the Funding team is focused specifically on funding members of the Rust Project for their maintenance work on the Rust toolchain. While that might include also some development of new features, that is typically not the primary goal of the funding that the team provides; funding large-scale feature development is under the scope of Rust [Project Goals][goals].

The words Rust Project contributors and maintainers are used interchangeably within this document. They refer to members of the Rust Project who contribute to the Rust toolchain (i.e. projects and repositories under the `rust-lang` and related GitHub organizations).

## Activities of the team

Below is a non-exhaustive list of activities that the team is expected to perform to fulfill those duties:
- Communicate with Rust Project teams to learn about their maintenance needs and other kinds of desired support.
- Communicate with Rust Project members to learn about their funding needs and other kinds of desired support.
- Distribute available funds to financially support Rust Project contributors, based on evaluating the most pressing maintenance needs of Rust Project teams.
- Ensure the success of, and run, the Maintainer in Residence program, as defined by [RFC #3931][rfmf-rfc].
- Support Rust Project contributors via [grants].
- Ensure that Rust Project contributors funded by this team are satisfied with their arrangement, are not blocked from doing their designed work, and are not under undue pressure from funders.
- Promote the work of Rust Project contributors funded by this team and its positive effect on the Rust Project to attract more funding, for example by writing blog posts or recording podcasts or videos.
- Communicate with funders (both companies and individuals) to find new funding opportunities and ensure that they are satisfied with the way their provided funds are being spent.
- Provide funding suggestions to external maintainer funds or companies interested to hire maintainers themselves, to help steer funds not managed by the Funding team itself towards the betterment of the Rust Project. The Funding team may also pool funds with such funding entities to co-fund Rust Project contributors.
- Help finding long-term sustainable funding and new funding sources to sustain Rust Project contributors, for example by coordinating promotional fundraisers together with the Rust Foundation.
- Responsibly manage the available budget and the funds from the Rust Foundation Maintainers Fund, to ensure long-term sustainable funding for Rust Project contributors.
- Communicate with the [goals][t-goals] teams to ensure that maintainers are properly supported to provide reviews and maintenance of accepted Rust [Project Goals][goals].
- Work in the open, unless the discussion requires privacy (for example personal or hiring, funders' interests, etc.), by sharing its meeting notes publicly and proactively sharing their plans with Rust Project members.
- Publicly document its decision-making processes, funding decision rationale and funding program details.
- Be open to feedback about their processes and funding decisions, in particular from other Rust Project members.
- Work actively, to ensure that funding opportunities are not wasted unnecesarily, and that Rust Project members are not unnecessarily delayed from receiving funds that are allocated for contributor support.

[rfmf-rfc]: https://rust-lang.github.io/rfcs/3931-rfmf-rust-foundation-maintainer-fund.html
[grants]: https://github.com/rust-lang/leadership-council/issues/301
[t-goals]: https://rust-lang.org/governance/teams/#team-goals
[goals]: https://goals.rust-lang.org

Given the amount of influence that the Funding team holds, due to being responsible for dispersing funds amongst Rust Project members, its membership and affiliation rules are more complex than for most other Rust teams. This charter thus also documents several rules below.

## Team membership

The members of the Funding team are selected by the Rust Leadership Council. The Council ensures that the team is staffed with enough members, as there is a lot of continuous work to do in the team. Ideally, the team should always have at least four members.

The Council is encouraged to examine the membership of the team at a regular cadence (e.g. every six months) to ensure that its members still want to actively participate in the team activities. This opportunity can be used to add more members to the team, if it is understaffed, or remove members that no longer want to be a part of the team. The Council will ask for nominations for new Funding team members from Rust Project members.

When the team membership is updated, we suggest for the members who are stepping down to help with onboarding new team members for some time, to ensure continuity.

Members of the Funding team must be, and remain, in good standing with the Rust Project. The moderation team should be consulted prior to adding a new member to the Funding team.

The Funding team has a special and tight relationship with the Rust Foundation, which handles the funding budget, contracting, legal matters and the Rust Foundation Maintainers Fund, which is the primary source of funds that the Funding team works with. Because of that, at least one member of the Funding team always has to come from the Rust Foundation, to streamline communication with the Rust Foundation and provide better insight into financial and budgeting matters.

The Council is also encouraged to consider having at least one member of the Funding team be a part of the Project's governance (either a Council member or a Project Director), to facilitate communication between the Funding team and the governing bodies of the Rust Project.

The Funding team selects its lead(s) amongst themselves.

## Affiliation limits

Funding team members are subject to affiliation limits, to avoid disproportionate influence of companies or other legal entities on its agenda. No more than one member of the Funding team may come from the same company, legal entity, or a closely related set of legal entities.

If this limit is breached due to employment changes, the affected members should come to an agreement to decide which one of them will step down. If they cannot agree on this, the Leadership Council should promptly decide it.

The affiliation limit does not apply to the Rust Foundation; there might be multiple Funding team members affiliated with the Rust Foundation specifically, as many Rust Project members may be somehow affiliated with it.

For more details about affiliation limits, see the [Leadership Council Affiliation policy][lc-affiliation-limits], upon which this rule is based.

[lc-affiliation-limits]: https://rust-lang.github.io/rfcs/3392-leadership-council.html#limits-on-representatives-from-a-single-companyentity

## Conflicts of interest

Given that the Funding team members are themselves members of the Rust Project, they might be interested in being financially supported by the Funding team. Amongst other things, this could actually help their Funding work itself, as it can be quite time intensive. A similar situation can happen with Leadership Council members, who might also want to ask for funding.

However, it is also of course a clear conflict of interest, both for members of the Funding team, but also members of the Leadership Council, because it holds a lot of direct influence on the Funding team. We will use the term "conflicted candidate" in the rest of this section to refer to Funding team or Council members asking for being funded by the Funding team.

We instate the following rules to lessen (though not completely remove) the described conflict of interest.

Conflicted candidates may ask to be financially supported by the Funding team for a specific role (e.g. being a MiR for team `X`), but this comes with caveats:
- They must not vote on themselves.
- They must not privately discuss the role that they are actively applying for (or being considered for) with the funding team, funding team advisers, or Leadership Council.
- They must abstain from all decisions made about the role that they are actively applying (or being considered) for. This includes decisions whether the given role (or supported team) should be prioritized against other considered roles.

Additionally, if the Funding team decides to financially support a conflicted candidate, that decision has to be explicitly approved by the Leadership Council prior to being finalized. If the conflicted candidate is a member of the Leadership Council, they have to abstain from this approval.

The Funding team is also encouraged to discuss decisions to fund conflicted candidates with the broader Rust Project, to gather feedback on it.

Note that the Funding team primarily decides which *teams* to support, and only then should they look for candidates that could support those teams. When making those decisions, they should strive to decide as if the conflicted candidate was any other Project member.

### Conflicts of interest rule rationale

There are two primary factors that cause a conflict of interest in this situation: the Funding team member actively participating in the decision to fund themselves, and the Funding team member having influence that affects the decisions of other Funding team members.

The first conflict is resolved by the described rule; Funding team members cannot vote on themselves nor participate in any decisions leading to themselves being funded by the Funding team.

The second conflict is much more difficult to resolve. Suppose that we forbid Funding team members from being funded completely, to ensure that their Funding team membership will not influence their colleagues' decisions. If a Funding team member would need funding, they would thus have to step down from the team. But even that would not completely remove their influence on other members of the team! It would still be their former colleague, with which they worked recently.

How much time would they have to wait to remove any semblance of a remaining conflict of interest? Or would a former Funding team member be banned from getting funding even after leaving the team? While in the meantime, they might reduce or stop their contributions due to not getting the necessary funding, and the team they were supposed to support will miss out (unless there is someone else the Funding team could hire instead). The Funding team itself might also lose an opportunity to help their inner workings by having an additional person on the team being funded.

The reality is that there is some amount of conflict of interest with almost any candidate who asks for being funded. Members of the Funding team might be team colleagues with the candidate in other teams, as many Project contributors are members of several teams. And even outside of team boundaries, many people within the Project know each other and are acquaintances, if not outright friends.

The (relatively permissive) rule thus acknowledges that this conflict can exist regardless of whether the candidate is a Funding team member or not, and puts trust into the Funding team members to decide what is best for the Rust Project.

It also adds an additional safety guard on top by requiring the Leadership Council to explicitly confirm financial support of Funding team members. This would also prevent a (theoretical!) possibility where the members of the Funding team would collude and cross-fund each other, even if that would not in the best interest of the Rust Project.

## Relation to the Leadership Council

Given the amount of influence that the Funding team has, it has a special relation with the top-level governance body of the Rust Project, the Rust Leadership Council:
- The Funding team is a subteam of the Rust Leadership Council.
- The Leadership Council determines the membership of the Funding team.
- The Leadership Council has to approve (as noted above in [Conflicts of interest](#conflicts-of-interest)) any funding that the team allocates to a member of the Funding team itself or to a member of the Leadership Council.

The Funding team also has to report its budget (i.e. how much money it has and expects to spend in the following year) and funding status (how are MiRs happy with their role, what is the status of finding new funding sources, etc.) many it plans periodically, at least once a year. So that the Council can take these things into account when planning its own Project Priorities budget.
