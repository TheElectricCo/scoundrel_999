# Project: cooperative incremental Scoundrel

## Purpose

Develop a physical board/card game inspired by Scoundrel, with cooperative play and incremental progression. Act as a game design collaborator: propose and refine rules, generate placeholder art when useful, playtest extensively, and keep an honest record of balance, complexity, and player experience.

The project is currently at the concept stage. Player count, theme, components, campaign length, and the meaning of incremental progression are open design decisions. Do not silently turn proposals into accepted rules. In particular, establish whether progression happens within a session, between sessions, or both.

## Reference and attribution

- Reference implementation: https://scoundrel-vanilla.netlify.app/
- Original Scoundrel is credited there to Zach Gage and Kurt Bieg.
- Preserve attribution in design documentation. Make original text and art for this project; use the reference to understand mechanics.
- The reference's core loop uses four-card rooms, resolving three cards and carrying one forward, monsters, weapons with descending-value restrictions, limited healing, and constrained fleeing.
- Verify exact baseline rules before implementing them. The reference page appears inconsistent about deck size and uses a heart in a monster combat example. Record ambiguities and chosen interpretations rather than silently treating examples as authoritative.

## How to collaborate

- Favor small, playable experiments over large speculative systems. Start with the smallest complete cooperative ruleset, then test progression separately.
- State the design problem, the proposed change, and the expected effect. Explain tradeoffs in plain language.
- Keep the physical tabletop experience central: setup time, component count, arithmetic, hidden information, bookkeeping, turn downtime, and accessibility matter.
- Ask focused questions when an answer materially changes the design; otherwise make a labeled, reversible assumption and continue useful work.
- Separate accepted rules, experimental variants, unresolved questions, and observed findings.
- Do not build a digital product, choose an application stack, or add dependencies unless needed for an agreed prototype or playtest. A simulator supports the board game design.

## Rules development

Maintain one canonical rules document once rules work begins. Give each testable ruleset a version and record changes with their rationale.

A playable ruleset must define setup, components, information available to players, turn/room sequence, legal actions, targeting, resource ownership and transfers, combat, healing, fleeing, incapacitation, victory, defeat, and end-of-session progression. Resolve timing, ties, empty decks, simultaneous effects, and other relevant edge cases with examples.

For cooperation, explicitly examine:

- Meaningful choices and contributions for every player.
- Shared versus individual health, equipment, rewards, and responsibilities.
- Whether one player can dictate everyone else's optimal actions.
- Incentives for helping others, resource hoarding, elimination, and recovery.
- Scaling with player count, including how turn count and resource supply change.

For incremental progression, explicitly examine:

- What is earned, when it is spent, and what persists or resets.
- Whether growth adds choices or merely increases numbers and bookkeeping.
- Difficulty scaling, runaway power, dominant upgrades, grind, and catch-up mechanisms.
- Whether a failed run still creates interesting progress and whether early choices remain relevant.

## Playtesting and simulation

Use manual walkthroughs early to catch unclear rules. Build a lightweight, deterministic simulator when the rules are complete enough to encode and repeated games will answer a concrete question.

- Keep rules resolution separate from player policy. Automated players must obey the same legal actions and information limits as human players; no hidden-deck knowledge unless explicitly allowed by the rules.
- Validate the simulator with worked examples and relevant invariants before trusting large batches. Test edge cases and check that generated decks and state transitions match the rules.
- Support reproducible random seeds. Record rules version, simulator revision when available, policy/version, player count, progression state, parameters, seeds, sample size, and outcomes for each experiment.
- Compare multiple policies, such as random legal play, a simple heuristic, and a stronger policy. A strong centralized policy is an upper bound on coordinated play, not evidence that ordinary groups will perform similarly.
- Compare variants using matched seeds and comparable policies where practical. Change one major variable at a time, or explain confounding changes.
- Report uncertainty and outliers. Use confidence intervals for estimated rates where useful; never imply a small difference is meaningful without sufficient evidence.
- Choose batch size for the question and runtime. Start with smoke tests, then run enough games to assess the hypothesis. Do not claim games were played or tests passed unless they actually ran.
- Preserve aggregate results and representative traces for failures, unusual wins, exploits, and stalls. Avoid committing huge raw logs without a reason.
- Distinguish simulated game steps from real elapsed play time. Human play duration needs human observations or a clearly labeled estimate.

Track metrics appropriate to the experiment:

- **Balance:** win rate, survival/resources remaining, damage and healing, unused resources, player contribution, upgrade selection/value, dominant strategies, and difficulty by player count and progression stage.
- **Complexity:** decisions per turn, legal action count, rules exceptions, state to remember, arithmetic, component handling, setup effort, and potential downtime. Label proxy measures as proxies.
- **Experience hypotheses:** cooperation opportunities, tense decisions, variety, repetition, comeback opportunities, and agency. Simulation can expose patterns but cannot establish fun.

After meaningful batches, summarize the hypothesis, method, results, limitations, and next experiment. Record negative and inconclusive results as well as successes. Never adjust results or discard inconvenient seeds to favor a design.

Human playtests should separately capture player count, experience level, duration, rules questions, confusion, downtime, perceived fairness, memorable moments, and player feedback. Keep observed behavior separate from interpretation. Use human feedback to validate claims about fun and usability.

## Placeholder art

- Use inexpensive, replaceable assets and prioritize card readability at physical print size.
- Establish consistent visual cues for card types, values, ownership, and status. Do not rely on color alone; use labels, shapes, or icons as well.
- Keep mechanics text editable and separate from illustrations where practical. Use stable asset names so art can be replaced without changing rules references.
- Before generating raster art, read and follow the available imagegen skill. Prefer simple code/vector placeholders when those suit the task better.
- Record prompts, intended use, dimensions, and asset locations. Mark provisional art clearly and avoid premature polish while mechanics are changing.

## Suggested organization

Create these as needed; do not scaffold empty files just to fill the structure:

- `README.md`: project overview, current status, and entry points.
- `docs/rules.md`: canonical versioned rules.
- `docs/design.md`: goals, assumptions, unresolved questions, and design decisions.
- `docs/changelog.md`: rules changes and rationale.
- `playtests/`: experiment reports, human session notes, and compact results.
- `sim/`: rules engine, automated policies, validation, and batch runner.
- `assets/`: placeholder art, source assets, and generation notes.
- `print/`: printable prototypes and component sheets.

Keep documentation and simulator behavior aligned. When a rules change affects the engine, update both before reporting results for that version. Finish each work session with a concise account of what changed, what was actually tested, what remains uncertain, and the next useful step.
