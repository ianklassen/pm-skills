# PM Skills

Product management, as a set of skills for AI coding/building tools. Not a prompt library: a set of reusable judgment.

## Why this exists

Most published skill repos are written for engineers: TDD discipline, codebase architecture, debugging workflows. Almost nothing exists for the other half of building products: the ambiguous, judgment-heavy decisions PMs make constantly, that don't have a "run the tests and see" feedback loop.

This repo is an attempt to encode that judgment the same way engineers encode theirs: as skills an AI agent (or a person) can consult, not just a folder of document templates.

## Two kinds of skill, on purpose

**Decision skills**: take a situation, return a judgment. "Should I message the customer about this?" "What can I actually cut from this scope?" "Is this worth escalating?" These are the harder, more valuable half. A decision skill should make you *more* likely to disagree with your first instinct, not just confirm it.

**Artifact skills**: take inputs, produce a document. Specs, stakeholder updates, tickets. Useful, but not where the differentiation is, since most PM tools already do a version of this.

Every decision skill should be usable standalone, without any AI tool at all. It's a framework a human can run in their head. The AI wrapper makes it faster and more consistent to apply, it isn't the point of the framework.

## Structure

```
pm-skills/
├── decision-skills/
│   ├── when-to-not-message-the-customer/
│   ├── scope-cut/
│   └── escalation-judgment/
└── artifact-skills/
    ├── spec-from-conversation/
    └── stakeholder-update/
```

Each skill is a single `SKILL.md`: portable markdown, works as a Claude Skill, a Cursor rule, a Codex instruction, or just a doc you read before making a call. No lock-in to one tool by design.

## What makes a good decision skill (the format, if you're contributing)

Every decision skill in this repo follows the same shape:

1. **The judgment it encodes**: why the default instinct is often wrong, named specifically, not just "use good judgment"
2. **The decision framework**: an ordered set of questions, not a checklist to satisfy in any order. Order matters: some questions override everything after them.
3. **A fast reference table**: the framework compressed to scan in ten seconds when you're mid-conversation and don't have time to read prose
4. **What to watch for**: specific ways people miscalibrate this exact decision, in either direction
5. **Output format**: what invoking the skill should produce: a recommendation and the reasoning, not a wall of text

A decision skill that just says "it depends, consider the tradeoffs" has failed. The point is to actually take a position given the framework, the same way a real senior PM would in the room.

## On placeholders

Some sections in these skills are marked **[PLACEHOLDER: needs real material]**. These are deliberate, not oversights.

The framework parts of a decision skill can be reasoned out. The *what to watch for* and *worked example* sections can't. They have to come from having actually made the call and sometimes gotten it wrong. Writing those from theory produces exactly the generic "consider the tradeoffs" advice this repo exists to avoid, so they're marked open until they can be filled from real experience.

If you're forking this, the same applies: the placeholders are where your own scar tissue goes, and that's the part that makes your version worth more than the template.

## Status

Early. Three decision skills, two artifact skills. Frameworks are drafted; experience-derived sections are marked as placeholders pending real material.

`scope-cut` has been pressure-tested against a constructed scenario and revised (added an authority check for publicly/contractually committed scope, a measurement-dependency test for load-bearing items, and an explicit quality-axis pass). The other skills haven't had that treatment yet.

Contributions and disagreements welcome, especially disagreements. If a framework here doesn't match how you've seen a good PM actually make this call, open an issue.

## License

MIT
