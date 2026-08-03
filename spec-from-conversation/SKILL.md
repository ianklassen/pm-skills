---
name: spec-from-conversation
description: Turn an unstructured stakeholder conversation, Slack thread, or meeting transcript into a structured spec (problem, goals, non-goals, success metrics, open questions). Use whenever a PM has raw conversational input and needs a first-draft spec, or when someone says "can you turn this into a doc" after a discussion. This is an artifact skill (produces a document), so pair it with a decision skill like scope-cut once the draft exists, don't use this to also decide what should be in scope.
---

# Spec From Conversation

## What this does

Takes messy input (a transcript, a thread, rambling notes) and produces a structured first-draft spec. This skill produces a *draft to be argued with*, not a final document. It should surface ambiguity the conversation left unresolved rather than silently resolving it for the reader.

## Process

1. **Extract, don't invent.** Pull the problem statement, goals, and constraints only from what was actually said. If the conversation didn't settle something (e.g., no one said what "done" looks like), write it into "Open Questions," don't guess a metric that sounds plausible.
2. **Separate stated goals from implied ones.** If a stakeholder said "make it faster" but never gave a number, the spec should say "faster (no target given, needs follow-up)" rather than picking 200ms because it sounds reasonable.
3. **Draft non-goals explicitly**, even if the conversation never mentioned them. A spec with no non-goals section is usually a spec that will grow scope silently later, so flag anything adjacent that was implicitly excluded (e.g., "web only, per the discussion; mobile wasn't mentioned either way, confirm").
4. **Flag conflicting statements rather than resolving them.** If two people in the thread said different things, both go in with attribution, not a smoothed-over average.

## Output structure

```
## Problem
[What's broken/missing, from the conversation, in plain terms]

## Goals
[What success looks like. Flag any goal stated without a measurable target]

## Non-Goals
[What's explicitly or implicitly out of scope]

## Success Metrics
[Only include metrics actually discussed; otherwise list under Open Questions]

## Open Questions
[Everything the conversation didn't resolve. This section should not be empty on a first draft]
```

## What to watch for

Don't let this skill's output look more decided than the conversation actually was. A polished-looking doc with confident language creates false consensus, since stakeholders will assume agreement existed just because it's written down cleanly. When in doubt, under-resolve rather than over-resolve.
