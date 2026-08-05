---
name: when-to-not-message-the-customer
description: Decision framework for whether a product/customer communication should actually be sent, not just how to write it. Use this whenever a PM is drafting an incident update, release announcement, policy change notice, deprecation warning, or any customer-facing message, and especially when someone asks "should we tell customers about X?" or "draft an update about Y." Also trigger when reviewing a drafted comms piece before it ships, or when a team defaults to "just send an update" as a reflex rather than a decision. This skill does NOT write the message: it decides whether, when, and to whom a message should go, and hands off to a writing step only after that's settled.
---

# When to Not Message the Customer

## The judgment this encodes

Most comms guidance is about tone and clarity. This skill is about the decision that comes before that: **should this message exist at all, right now, to this audience?**

The default reflex on a team is "communication is good, more is better, when in doubt send it." That reflex is wrong more often than it looks, because messaging has real costs that don't show up until later:

- **Erodes signal.** Every message you send trains customers on how much attention future messages deserve. A team that messages on every minor blip teaches customers to ignore all of them, including the one that matters.
- **Manufactures anxiety.** A status update sent because the team feels like it should say *something* can convert a non-event into a perceived crisis in the customer's mind, purely because "why would they be telling me this."
- **Locks you into a narrative before you have the facts.** An early, well-intentioned update ("we're aware of X, working on it") can pin you to a story that changes three hours later, forcing an awkward correction that damages trust more than silence would have.
- **Solves the team's discomfort, not the customer's problem.** A lot of "let's send an update" instinct is really the team wanting to feel like it's doing something. That's a legitimate feeling and a bad reason to message.

None of this means "default to silence." Silence has its own failure mode: customers who find out from someone else, who feel stonewalled, or who make a worse decision because they didn't have information you had. The skill is picking the right side of that line on purpose, not by reflex in either direction.

## The decision framework

Work through these in order. Stop and message as soon as a "yes" forces your hand, and don't keep evaluating past the point of clarity.

### 1. Does the customer need to *act* differently because of this?

If yes (they need to change a workflow, expect downtime, migrate before a deadline, or a decision they're mid-way through is now based on stale information), **message**, regardless of how the other questions resolve. Actionability overrides everything else below.

If no, keep going.

### 2. Will they find out anyway, and does the finding-out channel matter?

If this will surface on a status page, in a support ticket someone else already filed, in the press, or in a competitor's marketing, the question isn't "should we message," it's "do we want to control the framing." Silence here isn't neutral: it's ceding the narrative. **Message**, proactively, before the alternate channel gets there first.

If this genuinely won't surface elsewhere, keep going.

### 3. Is this actually resolved, or are you updating on an update?

Check whether the underlying issue is stable enough that the message won't need a correction within 24-48 hours. An update sent from uncertainty ("we believe this is now resolved, we'll confirm") reads as confident even when you don't feel confident, and a walk-back costs more trust than a slightly later, more certain message would have. If you're not sure it's actually resolved: **wait**, or send something explicitly framed as provisional rather than resolved, and be honest with yourself about which one you're doing.

### 4. Who specifically is affected, and is that different from who's on the send list?

The default send list ("all customers," "the whole workspace") is usually wrong. A scoped incident affecting 2% of accounts, blasted to 100%, teaches the other 98% that your alerts are noisy and not-for-them, which is the erosion-of-signal cost from above, self-inflicted. Segment the list before deciding to send at all; sometimes the right answer is "message, but only the affected cohort," which looks different from both "message everyone" and "don't message."

### 5. What does silence cost, specifically, not generically?

Don't accept "customers like to be kept in the loop" as a reason on its own; it's true of almost everything and therefore decides nothing. Name the specific cost of staying silent in this instance: a support ticket spike, a specific churn-risk account asking pointed questions, a compliance/SLA obligation. If you can't name a specific cost, that's evidence the message is optional, not required. That doesn't mean don't send it, but changes it from a "must" to a "team's choice, weigh against the costs in the top of this doc."

## Fast reference

| Situation | Default lean |
|---|---|
| Customer needs to take an action | Message, always |
| Will surface elsewhere regardless | Message, proactively, to control framing |
| Status genuinely uncertain / still shifting | Wait, or send provisional-labeled only |
| Affects a narrow segment | Message that segment only, not the full list |
| No named specific cost of silence | Optional: team judgment call, lean toward restraint |
| Team wants to message mainly to feel like it's doing something | Don't message; find the team a different outlet (internal update, not customer-facing) |

## What to watch for in yourself

- **Confusing "we could write something" with "we should send something."** Drafting is cheap and doesn't obligate you to ship.
- **Over-rotating after getting burned by silence once.** One bad experience with under-communicating can flip a team into over-communicating for months. Both are miscalibrations of the same skill.
- **Letting comms become a proxy for progress reporting to your own leadership.** If the real audience for the update is your VP, not the customer, don't dress it up as a customer message.

## Worked example

> **[PLACEHOLDER: needs real material]**
> One walkthrough of a real comms decision. Most valuable version: a case where the framework says **don't send** and that turned out right, since "we sent an update" is the easy story and "we deliberately stayed quiet" is the one people don't have a model for.
>
> Structure: the situation → which question drove the call → what was decided → what actually happened → what the alternative would likely have cost.
>
> Candidate sources: an incident that affected a narrow segment where the instinct was to blast everyone; a case where waiting for certainty avoided a public walk-back; a case where the team wanted to message mainly to feel productive.

## Output format when this skill is invoked

Don't jump straight to drafting. State explicitly:
1. The recommendation: message / don't message / message a narrower segment / wait
2. Which question in the framework above drove the call
3. If "message": who exactly, and what the one thing they need to know or do is (this becomes the brief for an actual writing pass, not the message itself)
