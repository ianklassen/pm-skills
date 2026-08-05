---
name: scope-cut
description: Decision framework for what to cut when a spec, sprint, or launch is too big for the time or team available. Use whenever a PM says a scope needs to shrink, a deadline is fixed and the work isn't, or someone asks "what can we cut" or "what's the MVP version of this." Also trigger when reviewing a spec that feels bloated before it goes to engineering. Distinct from prioritization frameworks (RICE, MoSCoW): this is specifically about which cut preserves the point of the release versus which cut guts it while looking similar on paper.
---

# Scope Cut

## The judgment this encodes

Most scope-cutting defaults to cutting whatever's easiest to cut, or whatever the loudest stakeholder didn't ask for. Both produce a smaller release. Neither reliably produces a release that still proves what it needed to prove.

The question that actually matters: **what is this release for, and does the cut version still do that?** Two releases can be the same size on a ticket board and be completely different in whether they were worth shipping.

## The decision framework

### 0. Separate what you can cut from what you can only renegotiate

Before sorting anything, identify scope that isn't actually yours to cut:

- **Publicly committed**: named on a landing page, announced at an event, in a press release
- **Contractually committed**: in an SLA, a signed enterprise deal, a partner integration agreement
- **Externally dependent**: another team or partner has already built against it

These are not cut decisions. They're renegotiations or escalations, and treating them as cuts is how PMs blow up trust with marketing, sales, and partners. Route them out of the cut list first and handle them separately (see `escalation-judgment`). What remains is your actual decision space.

### 1. Name the riskiest assumption the release is meant to test

Every release exists to learn or prove something: that customers want this, that this technical approach scales, that this workflow reduces support load. If you can't name that in one sentence, stop and get that answer before cutting anything; you'll cut the wrong things.

### 2. Sort scope into three buckets, not two

- **Load-bearing**: removing it means the release no longer proves what it set out to prove. Two tests, both of which must pass: (a) does the customer-visible value survive this cut, and (b) **can you still tell whether it worked?** The second test catches things that look like decoration but aren't: instrumentation, analytics events, logging, a control group. Invisible to customers, load-bearing to the release, and the single most commonly mis-cut category in this whole framework.
- **Supporting**: makes the load-bearing part usable/credible but isn't itself the test. Candidate for cutting to a rougher version, not necessarily to zero.
- **Decoration**: exists because it's nice, was requested by one loud voice, or "we're already in there." First things to go, no negotiation.

Most bloated specs got that way because supporting and decoration items were never separated from load-bearing ones, since everything got argued about with the same intensity.

### 2b. Sort the quality axis separately

Feature cuts are visible on a ticket board. Quality cuts aren't, which is why they're more dangerous and why they get made informally, mid-sprint, without anyone deciding. Explicitly list what's being reduced on each of these before you're forced into it silently:

- Error handling and failure states
- Edge cases and unusual inputs
- Test coverage
- Accessibility
- Performance under load
- Documentation and support enablement

Some of these are legitimate cuts for a time-boxed experiment. Accessibility usually is not, so check whether it's a legal/compliance obligation before treating it as optional. The rule is that a quality cut has to be a *stated* cut, with the same visibility as cutting a feature. Undocumented quality cuts are how a shipped release quietly becomes six months of support load.

### 3. Check whether "cut" and "phase" are being confused

Cutting removes something from this release's scope entirely, for now. Phasing removes it from this release's *timeline* while committing to it later. Teams that call a phase a cut end up quietly re-adding it mid-sprint because no one actually agreed it was gone. It just felt gone for a week. If something is being phased, say so explicitly and put a real placeholder (ticket, doc, date) so it doesn't die silently or resurface as scope creep.

### 4. Pressure-test against the stakeholder who'll be angriest

Before finalizing, ask: who is most likely to say "wait, where did X go" after this ships, and do you have an answer ready that isn't "we ran out of time"? If the honest answer is "we ran out of time" for something load-bearing, the cut is wrong, not the deadline.

## Fast reference

| Signal | What it usually means |
|---|---|
| Scope was announced publicly or is in a contract | Not a cut decision: renegotiate or escalate |
| Cut candidate removes something no one will notice missing | Probably decoration, safe cut |
| Cut candidate is invisible to customers but is how you measure success | Load-bearing despite looking like decoration, do not cut |
| Cut candidate makes the release harder to explain in one sentence | Probably load-bearing, don't cut |
| Quality reductions happening without being written down | Undocumented quality cut: surface it before it becomes support load |
| "We'll add it back next sprint" said with no ticket created | Not a phase, a cut in disguise, so be honest about it |
| The cut list was decided in five minutes | Probably cut by ease, not by importance, so revisit |

## What to watch for

> **[PLACEHOLDER: needs real material]**
> This section should be written from lived experience, not theory. Target 3-4 entries, each following the pattern: *the situation → the cut that was made → what it taught → the signal that now catches it earlier.*
>
> Candidate sources to draw from (GoPro / Intuit / McAfee / Apple / Amazon):
> - A quality-axis cut (error handling, edge cases) whose downstream support cost reshaped how you weigh those cuts now
> - A release where instrumentation was cut and the team couldn't tell whether it worked, which is where the measurement test in step 2 comes from
> - A publicly committed item treated as cuttable, and what that taught about checking authority before sorting scope
> - A cut that was correct where the communication of it mattered more than the decision
> - A time scope was successfully protected, and what made that possible
>
> Anonymize as needed: "a consumer hardware company" reads fine and keeps the lesson intact.

## Worked example

> **[PLACEHOLDER: needs real material]**
> One end-to-end walkthrough of the framework applied to an actual scoping decision. Should show the framework producing a *non-obvious* answer. If the worked example just confirms the intuitive call, it doesn't demonstrate value.
>
> Structure: the situation and constraint → step 0 authority check → the assumption → the three-bucket sort (including at least one item that got re-classified on inspection) → quality axis decisions → the final cut/phase list → what actually happened.

## Output format when this skill is invoked

1. Scope that isn't cuttable (publicly/contractually committed), routed out rather than cut
2. The one-sentence assumption this release needs to prove
3. The three-bucket sort (load-bearing / supporting / decoration), with measurement dependencies explicitly checked
4. Quality-axis reductions, stated explicitly rather than left to happen informally
5. Explicit list of what's cut vs. phased, with phase items given a real next step
6. The one stakeholder-pushback scenario this cut list needs to survive, and the answer ready for it
