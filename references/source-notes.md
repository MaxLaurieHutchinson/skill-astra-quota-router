# Source Notes and Attribution

## Primary inspiration

Original r/codex thread supplied by Max Hutchinson:

https://www.reddit.com/r/codex/comments/1w9ksnt/how_i_plus_user_dont_run_out_of_astra/

The original poster's useful insight is the starting point for this Skill: do not spend scarce Astra capacity on every step of a coding task. Keep the strongest model on high-leverage judgement and use cheaper models for bounded execution.

This repository intentionally does not reproduce the Reddit post. It converts the idea into a reusable Agent Skill.

## What was added in this implementation

The Skill adds a more explicit control layer around the original idea:

1. risk-based routing tiers;
2. deterministic-tool-first routing;
3. frontier-root and frontier-gated modes;
4. bounded work-pack contracts;
5. evidence return requirements;
6. evidence-driven escalation;
7. final frontier acceptance over real diffs/tests;
8. context-hygiene rules;
9. routing eval scenarios.

These additions are implementation choices in this repository, not claims about what the Reddit OP wrote.

## Why quota numbers are not hard-coded

Model availability, reasoning tiers, quotas, and relative consumption can change. The Skill therefore routes by decision risk and quality of returned evidence rather than fixed numerical multipliers.

## Attribution

Original workflow inspiration: the OP of the linked r/codex thread.

Skill adaptation: Max Hutchinson / MaxLaurieHutchinson.

If the original poster wants direct username attribution, corrections, or a different framing of the source idea, an issue or pull request is welcome.

## Non-affiliation

This is a community Skill. It is not authored, endorsed, or maintained by OpenAI and is not official guidance about subscription quotas.
