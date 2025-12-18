# Rust Foundation Maintainer Fund exploration document

The Rust Foundation is preparing a [Rust Foundation Maintainer Fund](https://rustfoundation.org/media/announcing-the-rust-foundation-maintainers-fund/) (RFMF) to financially support maintainers working on Rust. It has asked the Rust Project, through the Leadership Council, to help it prepare a strategy to decide how to get money from the fund to Rust maintainers.

This exploration document is a step towards that. It presents questions that we will eventually have to answer to provide a set of guidelines that will be used by the Rust Foundation to direct money from RFMF towards Rust Project maintainers. **It is meant to be a living document that is updated continuously while we gather ideas**. We welcome contributions to it!

This document primarily focuses on how to spend money of the Rust Foundation Maintainer Fund *specifically*, as it is timely; it wants to start in early 2026. This means that we have to work with constraints that are determined by the nature of this fund. We will attempt to justify all such cases in the [FAQ](#FAQ). Eventually, we could create a more generalized design that will be used to decide how to spend funds for maintainers that also come from other sources. But this is an explicit non-goal of this document.

The document is structured as a set of high-level questions that we will need to figure out. Each question contains a brief description, and then some possibilities that can be explored to answer the question, their trade-offs and other notes. Note that this document serves for *exploration*, i.e. enumerating ideas, possible options and trade-offs. A specific design for the fund, which should lead to an RFC, will be created later in a different document.

Before we get to the design space, we establish a set of things that are explicitly **out of scope** for this document:

- **How to get funding money**: This will be done by the Rust Foundation, and is not a part of this design. We work with the assumption that we will have a pile of (unrestricted) funds available, and our goal is to decide what to do with it.
  - That being said, we should also think about ways how we can e.g. do reporting or offer targeted work in a way that will attract (and sustain) sponsors. This might be a part of the initial RFMF RFC, or a later generalization.
- **Mentoring and onboarding junior maintainers or bringing in new outside people**: While this is a worthy goal and we might want to explore it eventually, for now we focus on getting money to people who already work on the Rust Project.
  - Bringing in "external" people (outside the Project) that then become a part of the Project is not completely new; it's how Rust Foundation Infrastructure Engineers work. And this model seems to be working well. But it's unclear whether that is a good fit for general maintenance, and we might not want to do that experiment as a starting point.
  - Note that mentoring and onboarding new contributors can still be a part of the funded maintainer's job description. We just do not consider funding external people, or having a junior maintainer internship program, at the beginning stages of RFMF.

> The set of out-of-scope assumptions above was written down to limit the design space, which is already large. If those assumptions change (e.g. we decide that we also want to consider people outside the Project), then the design space below has to be extended.

Some common vocabulary:
- Funded maintainer: A person that will be funded by RFMF to work on Rust.
- Decision group: A group of people that will decide who will be funded by RFMF.
- Maintenance: Work that benefits the long-term health of an open-source project or a repository. Typically includes doing code reviews, triaging issues, fixing critical bugs, writing and updating documentation or performing refactoring.
- Feature work: Work that is more targeted at implementing new features.

> Note: maintenance and feature work are rarely mutually exclusive, and often they complement one another. Many Rust contributors typically do both kinds of work.

## A: What do we want to fund?
There are various models that can be used to select what work we want to be funded. Here are some designs to explore:

### A1: General maintenance vs feature-specific work
[a1]: #A1-General-maintenance-vs-feature-specific-work

The fund is called "Rust Foundation Maintainer Fund", and the original idea was to fund *maintenance* (code reviews, refactoring, etc.), rather than specific feature development. Those two things are not completely unrelated, of course, as maintenance work can often *unblock* some follow-up feature work.

There are several possibilities to explore.

#### A1.1: Maintenance only/maintenance first
We say that the maintainers will be paid *primarily* for maintenance work. They could also do feature development, but it should not be written down in their "job description" as a large fraction of what they should be doing (or at least no specific features should be prioritized, otherwise it just becomes feature development).

**Pros:**
- It is the original goal of this fund: to pay people that do the unglamorous (but very much needed and incredibly important) maintenance work.

**Cons**:
- It can be difficult to explain the benefits and outcomes of maintenance work. That might make it harder to evaluate the results, and in turn find enough money to fund this kind of work.
- Doing *only* maintenance over a long-time period can be draining and can lead to burnout or lack of motivation.

#### A1.2: Targeted feature work
We could fund work packages that focus on unblocking and implementing specific features (e.g. `async Drop` or something in that vein).

**Pros**:
- It might be more interesting for companies if we tell them that we plan to fund specific feature work that might be interesting to them. That could bring more money to the table.

**Cons**:
- It goes against the spirit of a "maintainer fund", and might be better served by a different fund that uses restricted funding (such as e.g. the interop initiative).

#### A1.3: Something in-between/guided maintenance
Maintenance would be combined with feature work. For example, the funded maintainer could champion specific Project Goals and unblock people implementing that Goal. We can be flexible here, and for example have something like "70% is maintenance and 30% is unblocking/developing features".

**Pros**:
- It could help motivate companies to pay for such a maintainer, as it might directly help unblock work that is important for them, while also improving the health of the codebase in general.
- Has a nice synergy with companies paying people to do implementation work, while also contributing to paying maintainers that unblock that work.

**Cons**:
- The maintainer would have less time for general maintenance work

### A2: Funding people/teams/areas/work
[a2]: #A2-Funding-peopleteamsareaswork

We will need to decide *what we are funding*. Here are some models for deciding how to structure our funding objectives. Note that the models are not mutually exclusive, and we could choose different models for different funded positions.

#### A2.1: Fund maintenance areas
[a2.1]: #A21-Fund-maintenance-areas

We decide that we want to fund some general area (like a repository or a subset of a repository, e.g. compiler, standard library, Cargo, rustfmt, rustup, etc.). Then we select maintainer(s) that are knowledgeable in this area and can help with its general maintenance, such as code reviews, refactoring, etc.

**Pros**
- This kind of work is invaluable for improving the health of our projects and codebases, as it allows the person to do "whatever is necessary" to help the given area thrive.
- It is rather difficult to find funding for this kind of work through companies (compared to e.g. targeted feature work). General maintenance is often done only as a side-gig or by unpaid volunteers, which can lead to burnout. With RFMF, we could make it clear that we value this work, and properly support it.

**Cons**:
- It might be difficult to quantify what kind of work was done and how exactly it helped. This might not be a problem in practice though, as we will likely select maintainers that we trust and that interact with the Project on a daily basis, so it should be clear what kind of positive effect they have.

#### A2.2: Fund work packages
We could decide to fund more targeted work, which can be related to maintenance (e.g. finish a long-standing refactoring of X) but also feature work (unblock or finish the implementation of Y).

**Pros**:
- It is clear what the person should be working on, which makes reporting and evaluation of the work easier.
- The decision group would have more control over what exactly would the maintainer be doing. *It is unclear whether that is a good thing or not though.*

**Cons**:
- RFMF should provide stable and sustainable funding, which implies that it will last for some time (e.g. *at least* a year). It might be tricky to define work packages that can last throughout the whole funding, so it might require more back-and-forth between the maintainer and the decision group.

#### A2.3: Fund people
We could select a set of maintainer(s), fund them and trust them to do whatever is best for Rust. This is a model that e.g. the [Python Software Foundation][psf] uses for some of their Resident Core Developers.

**Pros**:
- Gives maximum flexibility to the maintainer, and allows them to work on things that are the most important for the health of the Project, rather than being bound by predetermined work scope.
- Demonstrates our trust in a given person, which could further help motivate their work.

**Cons**:
- Requires a lot of upfront trust (this should not be a problem when we fund existing Project Members that we know)
- It could make it more difficult to evaluate their work (same as [A2.1][a2.1]).
- It could cause allegations of "favoritism", as we select people first, work second. It is less transparent.

#### A2.4: Fund teams
A variant of the model above is not to select specific people, but select teams, and then delegate the funding decision to the team itself (e.g. "we give you 1 FTE, decide who amongst you will be paid").

**Pros**:
- The favoritism of the approach above is reduced, as we do not select specific people. But this just moves the problem of "who to select" from the Project leadership to teams or their leads.

**Cons**:
- This spreads the delegation of deciding who to fund quite a lot, and it puts the responsibility of evaluating the work on teams (and team leads) themselves. That could be overwhelming.
- Choosing who to pay amongst a small group might lead into personal conflicts. The team structure was not really designed for this, especially in smaller teams.
- The fact that many Rust contributors are in several teams also makes these kinds of decisions a bit awkward.

#### A2.5: Open proposals
We could use a "reverse model", where we let the maintainers themselves submit proposals on what they would think would be a valuable "maintenance work package". Then the decision group would evaluate the proposals and choose the best amongst them. This would be similar in spirit to the previous Grants program.

**Pros**:
- We do not need to decide top-level what are the important things to do. Instead, we let the maintainers tell us themselves.

**Cons**:
- Writing proposals is not fun, and puts additional burden on the maintainers to secure funding, rather than us identifying people who need it and supporting them.
- Feels more like a grant program rather than support for existing maintainers.
- Writing a catchy proposal for general maintenance work might be difficult, this might bias towards more high-profile/feature work.

## B: Maintainer role
We should clarify what does being a funded maintainer entails. For example, we could explicitly say that being in this role:
- Does not grant the maintainer any elevated *privileges* in the Project.
- Does not give the maintainer priority in RFC voting.
- Does not give the maintainer any extra weight or final say in reviews or any other decision process.

In general, being an RFMF-funded member of team `X` should not give additional privileges vs being a non-RFMF-funded member of team `X`.

We could also set some general rules about what the person is *supposed* to be doing, e.g. we could have a clause that tells the person that they should prefer doing code reviews before working on some new features that they like. This is highly dependent on the outcome of [A1][a1].

## C: Who chooses who gets funded?
[C]: #C-Who-chooses-who-gets-funded

Someone will have to be responsible for deciding who will receive the money from the fund (the "decision group"). The main goal of RFMF is to support the maintenance of Rust, so it seems natural that the Rust Project should decide on how to do that and who to fund. That still leaves a quite large group of people to decide though :)

One thing that should be taken into account is that members of the decision group might also want to get funded, so we should ensure that we document what to do in this case to avoid the conflict of interest.

> Note: there are many more possibilities to do here than what is presented below, including having companies being in the decision group. However, since we deal solely with unrestricted funding at the moment, it does not seem to make sense to involve entities outside the Project.

### C.1 Leadership Council
The Leadership Council already represents the Project as a whole, and consists of representatives of all top-level teams, so it could also serve as the decision group.

There are also other possibilities to explore here, e.g. combining the council with Project Directors, which are affiliated with the Rust Foundation, which could tie in the Foundation and the Project in this decision-making process.

**Pros**:
- The council is already responsible for distributing money given to the Project by the Rust Foundation, e.g. (travel) grants. This would be an extension of that responsibility.
- (Short-term benefit): We wouldn't have to appoint a new team, since LC already exists.

**Cons**:
- The current council was not elected with the knowledge that it would be responsible for distributing RFMF money *specifically*.
- Some current members of the council might be eligible/interested in funding from RFMF. Those members would of course be completely recused from participating in the selection process. They could be replaced by a different member of the team that they represent though; we already do this e.g. for Project Director elections. It could still be seen as a conflict of interest to be selected by the LC.

### C.2 LC + team leads
We could expand the set of Project representatives from the Council to e.g. team leads (currently ~40 people, but that includes teams that have multiple leads).

**Pros**:
- Team leads should have a good idea about the maintenance needs of their specific teams, and could thus evaluate which maintenance work would help the Project the most. (Note: it is unclear whether that means that they should also be making the decisions though, they could just provide their inputs to the decision group).
- A larger group will represent more viewpoints and teams (not just the top-level teams). In the council, there are teams that are represented by one representative, while some other teams only have e.g. only a `0.1` of a representative for themselves, since they share them with multiple teams.

**Cons**:
- Maintenance funding might not be relevant for all teams. Should we exclude those from the decision group? Or also let them vote?
- Making decisions in such a large group might be difficult.
- This provides more selection power to top-level teams, who would get represented both by their team lead(s) and by their Council member. We could also just remove the Council from the decision group and have only team leads to resolve this.

### C.3 Newly appointed individuals
The Leadership Council could point a set of individuals that would be making the decision. This group of people could be rotated on a regular basis to.

**Pros**:
- We would select a set of people with the prior knowledge that they will be responsible for making maintainer funding deciding (which was not apriori known when council members were last elected).
- We could avoid the conflict of interest entirely, e.g. by having a rule that members of the decision group cannot be funded by RFMF.

**Cons**:
- The decision problem just moves to a different place. How would we select members of this group? It seems that it would anyway fall on either the council or e.g. team leads, so it's unclear whether that would be so much better than either of those two making the decisions themselves.
- It would be a fairly special group that would hold a lot of "power" over Rust, so to speak. It could collide with our existing team structure hierarchy, and with the Leadership Council.

## D: Who is eligible to be a candidate for funding?
[D]: #D-Who-is-eligible-to-be-a-candidate-for-funding

We should provide a set of baseline requirements that will have to be met for someone to be considered to be a candidate for funding. This will be useful to have a quick reference for filtering out people that are not relevant for this role at all. The requirements should not be overly restrictive towards Project members though, because as noted in the intro, we *only* plan to consider existing Project members at this time.

Here are a few rules that we could set:

- The candidate should be a member of the Rust Project for some minimum duration of time.
  - We would have to clarify what does being a member of the Project mean? Member of a team? Or is a member of a working group/project group/marker team enough?
  - We would have to determine what should be the minimum duration? A year?
- The candidate must "bring their own r+ permissions". They must be able to perform maintenance, which includes merge/approval rights, on the repositories that they will be primarily working on.
  > Note: This would not make sense if we decide to bring in external people, but as noted in the intro, this is a non-goal at this moment.
- If the funded role is full-time, the candidate must not have considerable funding overlap (regardless of whether it's Rust or non-Rust) with the period when they are funded.
  - The "overlapping" part is important, it is of course fine to leave a job where they are paid to work on Rust too, and then become funded by RFMF instead.
  - The "considerable" part is important. If someone has GitHub Sponsors and receives $200 per month from individual contributors for working on Rust, this should NOT disqualify them from being funded by RFMF.
  - Note: this is just a normal expectation for someone that has a full-time job.
- If the funded role is part-time, the candidate may have funding overlap. However, if they have multiple sources of funding for Rust work (again, excluding smaller things like GitHub Sponsors), the maintainer should ensure that the funded work doesn't overlap or that they communicate clearly to their sponsors that some of their work might be funded from multiple sources (double-counting).
- We have to be able to pay the candidate in some way. This will not be an issue for most people, hopefully, but there are some considerations that have to be taken into account, for example sanctions. The Rust Foundation is a US-based entity and it has to abide by US rules.
- The candidate must not be in a conflict of interest. This will depend mostly on who will be deciding who should be funded, e.g. the candidate should not be in the decision group, or they should be recused from any participation in any selection process that involves themselves (not just the consensus process, but any evaluation or discussion).
- Similarly to the [rules](https://github.com/rust-lang/leadership-council/blob/main/roles/rust-foundation-project-director.md#requirements-and-eligibility) for selecting Project Directores, the maintainer must have (and keep) good standing with the Rust Project. And specifically, they must uphold the Rust [Code of Conduct](https://rust-lang.org/policies/code-of-conduct/).
  - In particular, we will not hesitate to enforce our Code of Conduct even if it would affect the maintainer's funding. Funded maintainers must, and will, be held to the same standard as everyone else in the Project.

## E: How to find candidates?
[E]: #E-How-to-find-candidates

This likely will not be a problem, especially at the beginning, but it is also something to consider. Note that this will heavily depend on the outcome of [A2][a2]. Multiple of those options could be combined:

### E.1 Open positions
We would open a "position" for a maintainer for a specific area within the Project, and let people sign up for that position, possibly with some lightweight statement (a.k.a. "mini motivation letter") where they would be able to explain why they are the best candidate.

**Pros**:
- It is transparent.
- Lets anyone enroll for a position (as long as we properly announce that the position is available).
- The statements might help us make decide who to select.

**Cons**:
- Might be a bit too much "bureacracy", especially at the start.

### E.2: Direct contact
We would directly ask specific people that we know are already doing
great maintenance work if they want to be funded by the RFMF.

**Pros**:
- It would make it easier to bootstrap the fund quickly at the beginning, as we have a relatively good idea of our existing maintainer fund, so we can ask people directly without having an explicit application process.

**Cons**:
- It is less transparent.

### E.3: Nomination process

Members of the Project could nominate candidates for consideration.

**Pros**:
- It is transparent.

### E.4: Application process

Similar to open positions, but the candidates themselves could propose the work that they would like to be doing.

## F: How do we prioritize who to fund amongst candidates?
This is possibly the hardest question of them all, because it is very likely that we will have more candidates and interested people than what we can "afford" with the Fund's money, especially while it is being bootstrapped. It will require us to determine what kinds of work in the Project are more important than others, and what maintainers we "prefer" to be funded, amongst a tight-knit set people who work with each other every day, who often know each other or are even friends.

> Note: this decision is very much relevant to [A1][A1], and answers to that question will likely heavily affect the answers to this question.

### F.1: Selection by the decision group
The decision group will gather inputs from various teams, automated metrics and other sources, and based on that, it will determine which maintainers will get funded for a specific funding period.

**Pros**:
- It allows us to capture the true needs of the Project in as much detail as we need, and use our best judgment and experience to decide which parts of the Project need funding the most.

**Cons**:
- It is hard to ensure that the decisions will be transparent. Ultimately, the Project would have to trust the decision group to do The Right Thing™.

Some additional notes/considerations:
- Should the "cost" of paying a given person (based on the determined reward amount) be used to determine whether we select them or not?
  - **Pros**: We could get more maintainers for a given amount of money.
  - **Cons**: It is not very fair to people e.g. living in more expensive countries, which would get a higher pay if we used an algorithm for it.
  - A way to avoid choosing based on pay is to simply order maintainers by some ranking/vote and then choose from the top until money runs out.
- There are also other aspects that could be used to determine priority, which cannot be determined by any kind of objective metrics. For example, judging how probable it is that we would lose a given maintainer if we cannot fund them.
  - Let's say that we have two maintainers, A and B, who both want to be funded by RFMF. If A doesn't get the funding, they know that they can likely land a decent job soon anyway, or they already have another job, and perhaps still have some off-time for a small number of contributions. While B might be unemployed, and if they don't get funding soon, they might lose their house rent, be deported from their country, etc. In that case we might choose to favor B.

Here is an example of an approach that we might take (note that this is really just a simple example):
- Ask each (non-trivial) team to come up with a list of "maintenance needs" that they have, and what is their current status - do they need maintenance help, do they already have people being paid to maintain the team's codebases, etc. This could be supported by automated tooling that would help quickly providing useful metrics from GitHub, and the data that we have from the Rust Project Contributor Survey.
- We sort these needs based on team size and "importance to the Project", which will be determined by the decision-making group.
- We allocate a set of "maintainer slots" to individual teams or maintenance areas.
- We [find candidates][E] and then select amongst them by a consensus or a voting process.

### F.2: Rule-based algorithm
We could create some "algorithm" that would decide which parts of the Project need (paid) maintenance the most, based on automated metrics, and decide the funding priority based on that.

**Pros**:
- Possibly the most transparent option, which does not allow much favoritism (except for gaming the ruleset itself).
- Removes people from the decision process, which makes it simpler and faster to decide. In fact, we would likely not even need a decision group in the first place.

**Cons**:
- It will be hard to come up with such an algorithm.
- It would only allow selecting a work area or a team, but not specific people (unless we want to also consider their metrics).
- Deciding based on metrics has all sorts of bias issues and favors people that could already spend a lot of time working on Rust before being funded by RFMF.
- Removes people from the decision process, which removes our ability to consider nuances.

## G: How to give the maintainers money?
We will need to pay the maintainers somehow. There are two main axes to think about here, part-time/full-time and employment/contracting/grants. As elsewhere, we could combine those approaches and use different models for different positions/maintainers.

### G1: Part-time vs full-time
Both approaches seem viable (and desired) by our maintainers.

#### G1.1: Part-time cooperation
**Pros**:
- This provides flexibility to the maintainers and can expand the pool of people willing to act as paid Rust maintainers.
- Some people do not want to leave their job and lose career progress to work on Rust, or just do not want to work full-time on Rust. A part-time collaboration could be a viable compromise for them, to support their existing Rust work.
- It could help us stretch our budget further.

**Cons**:
- Part-time cooperation might not be enough for long-term sustainable maintenance that provides stability to the maintainer.
- Some maintainers are only interested in switching to funded maintenance if it can be full-time, managing multiple jobs at once is difficult.
- We get less time from each funded maintainer, which may make it harder to have more frequent accomplishments with which to demonstrate accountability and seek more funding.

#### G1.2: Full-time cooperation
**Pros**:
- It gives the maintainer stability to fully focus on maintenance.

**Cons**:
- It is too inflexible for some maintainers, who would prefer to only work on Rust part-time.

### G2: employment vs contracting vs grants

Note that the Rust Foundation can currently primarily offer contracting or grants. It is unclear whether direct employment will be possible at the moment ([why?][faq-rf-employment]). We keep the employment option below for reference, and to make it clear that we have considered it.

#### G2.1: Contracting
Same as e.g. the Python or Zig Software Foundations, we could contract the maintainer based on the number of hours spent on Rust each month.

**Pros**:
- Relatively quick and easy to set up (for the Rust Foundation) and also wind down in case funds run out.
- Might result in more money ending up in the maintainer's pocket (w.r.t. taxes and insurance).
- For part-time cooperation, it seems to make more sense than part-time employment.
- Having a contract allows us to set some ground rules for how the maintainer's work will look like (unlike grants).
- Some people prefer the larger independence of contracting.

**Cons**:
- Does not provide as much stability to the maintainer as employment in terms of long-term support.
- Does not offer the same benefits as employment (health insurance, vacations, 401k, mortgage, visas, etc.).
- In some countries (e.g. Germany or France), full-time/single-source contracting is a legal gray zone that is close to being outright illegal.
  - It might require the maintainer to set up a "personal company" (e.g. a limited liability company), along with all the taxes and legal work that comes with it. But not even that can be enough; some maintainers reported that they were already checked by the tax office due to full-time contracting. In other words, in some jurisdications the only legal way to have a full-time single source income might be employment.
- It might be difficult to persuade some potential maintainers to switch from their current full-time employment to contracting.
- Due to the aforementioned challenges, some current maintainers would be unable to be funded if we only offer contracting.

#### G2.2: Grants
We could pay maintainers using grants, without any specific contracts.

**Pros**:
- It is a relatively light-weight option to pay someone, which does not require someone to have a (personal) company registered.
- It is a useful model for part-time work. We already have experience with this model from the Rust Grants program.

**Cons**:
- Similar to contracting, it does not provide stability or non-financial benefits to the maintainer.
- Similar to contracting, receiving a lot of funds through grants is a gray legal area and could trigger tax issues in certain countries (like Germany, France or Netherlands).
- We might be unable to have any sort of contract that would prescribe the ground rules of what the maintainer should be doing.

#### G2.3: Employment
[G23]: #G23-Employment

> Note: Direct employment might not be offered by RFMF ([why?][faq-rf-employment]).

The maintainer could be officially employed, either by the Rust Foundation, or some intermediary, to work on Rust.

**Pros**:
- It give the most stability and a "safety net" for the maintainer, especially around things like vacations, "401k", medical benefits, etc.
- It can be the only way to persuade people who currently have a full-time employment to switch to working on Rust instead.
- It might provide a better CV entry and career reference.
- It can be useful for avoiding visa problems or getting a mortgage.
  - Some people actually need to be employed by a local company in their country for visa reasons.

**Cons**:
- Requires a long-term/repeatable source of funding, otherwise the job stability could not be upheld. (This is the main reason why employment will not be available from RFMF at the beginning)
- More overhead to set up for the Rust Foundation.
- It could be problematic to hire people from certain countries. This could be potentially resolved by hiring through intermediaries.

#### G2.4: Let the maintainer choose
If we are able to support multiple models, we could simply let the maintainer choose.

**Pros**:
- Most flexible for the maintainer.

**Cons**:
- Requires the RF to support multiple options, probably requires more administrative work.

### G3: For how long will the contract/grant last?
Whatever model we choose, we should think about providing long(er)-term support to maintainers. It does not make much sense to fund *maintenance work* specifically e.g. for only six months, that's just a too small time period to even get fully up-to-speed or to have something to show for maintenance efforts. On the other hand, we might want to have some fixed duration, rather than having indeterminate contracts, as the funding source can run out.

Having a longer time commitment could also allow people that are currently employed to seriously think about quitting their current job to become a full-time Rust maintainer.

In the ideal case, 1 year should probably be a minimum, but 2-3 years would be even better. However, we have to be grounded in reality, and that reality might very well be that we simply cannot afford to pay someone e.g. for more than a year (before the next round of funding comes in). So ultimately, this will depend on how many funds RF is able to secure.

What we could do as a Project is to decide whether we want to spend a given amount of money to fund e.g. two people for a year or a single person for two years.

In any case, funding can always run out for various reasons, so we should prepare the maintainer for that possibility, and communicate often about the current state of their funding source.

We should also figure out what are the rules for prolonging a contract - if a maintainer's contract would automatically be prolonged if they are doing good work, or e.g. if they have to fight for the maintainer slot every time.

## H: How much money do we pay?
A tough question to answer, but one that we will have to resolve. In terms of state-of-the-art, the Python and Zig Software Foundations seem to pay around $60/hour to their funded core developers (mostly with contracting).

### H.1: Fixed amount
We simply set a single transparent baseline amount per hour, and use that for all maintainers that we fund.

**Pros**:
- The most transparent option.
- It does not require us to decide or negotiate what should we pay per each maintainer separately.

**Cons**:
- It does not factor in the cost of living and other factors. So it might be either very favorable or very unfavorable based on where does a person live.

### H.2: Fixed "levels" (e.g. junior/senior) with an established job ladder

We could have clear evaluation criteria for more junior and more senior engineers, with corresponding salaries. This means that rather than negotiating specific salaries, candidates are making the case for what "level" they get hired at, based on publicly documented criteria.

### H.3: Rule-based algorithm
We write down some rules and categories that will determine the amount of paid money based on the country where the person resides (cost of living), years of experience (within/outside the Project?) or even the kind of work that they will be doing.

**Pros**:
- Also relatively transparent, as we would just be following the algorithm to decide how much to pay someone, rather than coming up with arbitrary values per maintainer.
- It does not require us to decide or negotiate what should we pay per each maintainer separately.

**Cons**:
- Coming up with such an algorithm is hard, and it wouldn't allow us to make case-specific decisions (although it is unclear whether we would even want to make those).
- It would likely favor people that already had a lot of time to contribute before being selected to be a paid maintainer, and thus have good "GitHub metrics" (unless the rules are based solely on location or similar properties).

### H.4: Manual decision/negotiations
We could set up some (minimum) baseline amount of $, but then leave the final amount up to negotiations and personal considerations. We might want to set up some maximum range for better transparency.

**Pros**:
- We might be able to "land" maintainers that need to have a higher pay due to some specific considerations, that otherwise wouldn't accept the job if we paid the baseline rate. This might be worth it in certain cases.

**Cons**:
- People who will want to become maintainers might not be the best in negotiations.
- Each maintainer might be paid differently, which can in theory cause some envy and bad vibes.
  - Although many people already work on Rust while being employed by various entities and receiving very different amounts of pay, so this might not be such a concern.
- Negotiations take more time and effort from the decision group.

Some additional notes:
- Do we make the rate of each maintainer public, for maximum transparency? Zig does this, Python doesn't.
- Any notion of a "fixed amount" will of course eventually have to be updated over time, to account for inflation, industry trends, etc.
- We should clearly set the expectations that this is not a Silicon Valley-level job/pay, and it most likely will not be competitive with similar IT positions (at least from the start).
- We can use data from the Rust Project Contributor Survey here to figure out what the baseline should be.

## I: How will the maintainers report their work?
Given that the maintainers will be funded (likely with non-trivial amounts of money), we should set up some expectations around reporting. Even if we had total trust in the maintainer (which we likely would have) and did not require any reports from the Project side, some light reporting might be useful or even necessary to secure future funding for RFMF, so that companies can see some output of their donations.

Some considerations:
- **Period of the reports**: How often should the reports be made? This could range from having a periodic monthly or even weekly report to having e.g. a yearly or quarterly blog post that summarizes all work done over the given time period.
- **We should help the maintainer with reports**: The reporting should ideally be lightweight, and should not cause a big mental or time burden for the maintainer, as we want them to focus primarily on the maintenance work itself, not on stressing about reporting.
  - We could make use of existing structures within the Project (or establish new ones), e.g. the Program management program or t-content, to help with reporting and publicizing the maintainer's work. It might also be good to have some "buffer" between the maintainer and the entities evaluating those reports, especially if those are outside the Project.
- **Automation**: There are a lot of things that we could automate here, to gather all kinds of statistics on the maintainer's work. However, this should be mostly used to make it easier for the maintainer themselves to present what they did, not to directly evaluate their work based on those metrics, because maintenance work is so much more than what any kind of an automated metric could describe.

Some additional notes:
- This question is very much related to [C][C], but it is also slightly separate. For example, we could have the Project choose how we specifically allocate the funds, but then the maintainers might report their work also to the companies that provided the funds.
- A question that is related to both this and [C][C] is "who will the maintainers answer to". But maybe that can be the same as "who they report to".

Some state-of-the-art:
- [Django Fellows](https://groups.google.com/g/django-developers/c/Ujn3qif4U08?pli=1) used to provide weekly reports.

## J: Criteria for ending the funding?
Even though no one really wants to think about this, we should determine some rules for ending the funding of the maintainer prematurely (or not extending an ongoing contract/grant) in case the Project is not happy with their work. We should determine these rules proactively, even before the first such occurrence happens (and hopefully it never will).

Some possibilities for criteria that must be upheld, otherwise a contract/grant might be terminated:
- **The eligibility rules must still apply**: If the maintainer stops meeting any of the relevant [eligibility rules][D] during the period when they are funded, this should be ground for ending the contract/grant. For example, if they leave the compiler team and they are (supposed to be) doing compiler maintenance, it does not make sense to continue paying them. Or if they suddenly get hired for a full-time position elsewhere, that should also be grounds for ending stopping the funding.
- **High-impact work is delivered**: The work that the maintainer is doing should correspond to their "job description". If its nature changes a lot, we might want to evaluate if it still fulfills the goal of the role or not.
- **Communication**: The maintainer has to stay responsive and has to communicate with members of the Project, including the people who evaluate their work.

## K: How do we evaluate the success of the program?
It would be nice if we had some way to evaluate the success of the funding initiative (both as a whole and the success of funding individual people).

That can take various forms:
- Success is that we funded a maintainer, so that they were properly supported for their work.
- Success is that some objectively measured metric (e.g. PR review wait times, issue closure times, etc.) has improved in the area that the maintainer was working.
- Success is that people are less burnt out than before.
- Success is that we land high-value features that the community and industry are enthusiastic about, helped by the work of the maintainer.
- Success is that the regular reports of the program are highly regarded and garner substantial additional funding.

## L: How do we communicate the Fund?
This is kind of a meta question, but still an important one. Regardless of which approach we choose, we should take extra care to communicate how will the Fund work both to the Project, but also the outside world. We should coordinate blog posts and communication between the Project and the Rust Foundation, to avoid any misconceptions and confusion.

The running [FAQ][FAQ] at the end of this document should also help clarify (m)any common questions.

# State of the art
This section mentions how other programming language ecosystems deal with a similar maintainer support program.

## Python Software Foundation
[psf]: #python-software-foundation
The PSF (Python Software Foundation) has a [Developer in Residence](https://www.python.org/psf/developersinresidence/) (DIR) program that was started in 2021.

There are currently five developers in residence:
- Two of them are working specifically on security, packaging and similar topics. Those are sponsored by Alpha Omega, and they more or less correspond to the Rust Infrastructure, crates.io and security engineers employed by the Rust Foundation.
- Three of them do general maintenance work, including feature development. They are paid by a specific company (Bloomberg funds one position, Meta another, etc.) Those would correspond to maintainers paid by RFMF.

For some analogy, the PSF corresponds to the Rust Foundation. The Python open-source project then has a set of Core developers (those would correspond to Rust team members), and a Steering Council (SC), which is a top-level governing body. SC is most similar to the Rust Leadership Council (LC), although LC has mostly a delegation role, Rust teams make decisions on their own.

### Pay, length and funding arrangement
- Each person's pay is determined by the sponsoring company that provides funding for them. For the company sponsored roles, it is somewhere around $60/hour.
- The maintainer can choose whether they want to contract or be (remotely) employed through remote.com.
- The contract is for one year.

### Selection process
Once PSF gets funds for a new DiR position, they open a role, and anyone can sign up for it. The candidates then go through an interview process, which is conducted by both members of the PSF and the members of the SC. This is similar to how RF chooses Rust Infrastructure Engineers.

At the start, they wanted to prioritize choosing already established Core developers, rather than bringing in completely new people.

### Responsibilities
The responsibilities of DiRs is described [here](https://lukasz.langa.pl/a072a74b-19d7-41ff-a294-e6b1319fdb6e/#concrete-responsibilities). It is mostly:
- Doing PR reviews and issue triage.
- Investigate Python Project priorities and working on them.
- Maintain CI and the test suite.

### Reporting
The maintainers regularly meet with the Steering Council. They also write a report several times a year (although max. quarterly) to the sponsoring company.

The PSF also suggested the maintainers to write regular blog posts about their work.

## Zig Software Foundation
The Zig Software Foundation (ZSF) has a [Zig Core Team](https://ziglang.org/news/welcome-matthew-lugg/), which is a set of developers that can bill their hours spent on developing Zig to the ZSF. The compensation is $60/hour.

Zig gets their donations from [GitHub Sponsors](https://github.com/sponsors/ziglang), [Every.org](https://www.every.org/zig-software-foundation-inc) and [private company sponsors](https://ziglang.org/news/2025-financials/).

# FAQ
[FAQ]: #FAQ

## Can these guidelines be generalized for other sources of funding other than RFMF?
[faq-design-generalization]: #Can-these-guidelines-be-generalized-for-other-sources-of-funding-other-than-RFMF

Yes, eventually we plan to do that. But for now, this design is specifically focused on RFMF, to unblock it as soon as possible.

## Can the Rust Project fund maintainers directly?
[faq-project-direct-funding]: #Can-the-Rust-Project-fund-maintainers-directly

No. The Project is not a legal entity that could pay someone, nor can it even own money in the first place (that is why the Rust Foundation was created). What it can do, however, is tell some other entities with money how they should best use them to support the development of Rust. And that is exactly what the Project does with RFMF - it helps the Rust Foundation find the best way to sponsor Rust maintainers.

## Why can't the Foundation (directly) employ maintainers?
[faq-rf-employment]: #Why-cant-the-Foundation-directly-employ-maintainers

The Rust Foundation currently employs several people to work on Rust directly (e.g. the Rust Foundation Infrastructure Engineers). However, those positions are funded by restricted funds from the Alpha Omega initiative and other sources. Those funds are relatively stable and long-term, which enables the Rust Foundation to employ those people.

On the other hand, the Rust Foundation Maintainer Fund is (at least at the beginning) expected to mostly receive one-off donations from companies that might come in irregularly over the year. That does not provide enough long-term stability that would enable the Rust Foundation to offer long-term employments for the maintainers.

The Rust Foundation hopes that once the Fund has bootstrapped itself, it might be possible to also offer employment to provide more stable support for maintainers in the future.

That being said, the Rust Foundation is looking into supporting short-term employment contracts via remote.com to ensure maintainers don't have to set up their own limited liability company, take the risk (in some countries) that they can legally have a contract with employment-like restrictions, and get social security (including unemployment benefits if the contract is not renewed). This document will be updated once we have more information.

## Can't the Rust Foundation employ people through third-party entities?
[faq-rf-external-entities]: #Cant-the-Rust-Foundation-employ-people-through-third-party-entities

Some maintainers might need employment for various reasons (see [G2.3][G23]). Could the Rust Foundation contract to a third-party company that would employ them?

The Rust Foundation is willing to contract to small companies (such as a limited liability company) that are set up by the maintainer themselves, so that the maintainer can make full-time contracting legal in their country (when applicable).

Any fund taking money from the Foundation must make sure to understand and accommodate its constraints, legal or otherwise. Transferring the funds through third-party intermediaries can create legal and auditing risks for them. They have also expressed a strong preference for having a direct relationship with the maintainer, to ensure that the paid money will go (in full) to them, without management overheads taken by third-party intermediaries.
