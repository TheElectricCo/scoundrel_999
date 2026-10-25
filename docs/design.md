# Design notebook

## Decision status

**Accepted direction:** physical cooperative Scoundrel-inspired game; progression happens within a session (user, 2026-10-25). Between-session upgrades are outside this prototype.

**Reversible experimental assumptions:** exactly two players; generic dungeon theme; one ordinary deck; individual 12-health pools and equipment; alternating card actions; defeat when either player falls; one optional shared ability after four full rooms. These are proposals, not user-approved final mechanics. Canonical details live only in [rules.md](rules.md).

**Open:** desired difficulty, human session length, theme, larger player counts, whether a single upgrade provides enough progression, and whether early bad luck needs recovery. No campaign length is needed for a run that resets completely.

## Problems, proposals, and tradeoffs

| Problem | Proposed experiment | Expected effect and cost |
| --- | --- | --- |
| Shared solitaire can leave one person directing everything | Alternate actions; keep personal equipment and health | Both players act and own consequences. All information remains public, so quarterbacking is still possible; the active-player rule is a social boundary, not a mathematical solution. |
| Pooling everything removes distinct responsibilities | Personal weapons; potions can target either player | Choosing the next actor's room creates cooperation and healing someone else becomes useful. Mandatory equipping and no transfers may strand equipment on the wrong person. |
| Doubling solo starting health may erase pressure | Start at 12 each, 24 total | Leaves some shared cushion against split equipment. This number is an untested hypothesis; split health can make the team less resilient despite the larger total. |
| Individual elimination causes downtime | Any death ends the run for everyone | Nobody sits out; groups may find sudden team failure punishing. No recovery subsystem in this first experiment. |
| Growth can obscure the core balance | Compare base against one optional mid-run ability | Isolates growth from basic cooperation. Care and Guard create a choice with little writing, but may merely raise numbers and may have an obvious best answer. |

Helping is encouraged by shared defeat and targeted healing; there is no personal score or persistent loot to hoard. Weapon allocation is constrained rather than freely negotiated. Alternating actions means each full three-action room changes its starting player. With 44 resolutions in a completed run, each player resolves 22 cards regardless of flees. This does not guarantee equal combat contribution.

Only two players are supported. Adding players with extra health but no extra monsters would change difficulty; dividing the same health would change vulnerability and leave longer waits. Do not extrapolate this setup to three or four players without a separate version and test.

## Progression questions to test

The unlock is earned through room clearance, immediately chosen, and persists only to the end of that run. No spending, grind, catch-up currency, or difficulty scaling is introduced. The one-time unlock caps runaway growth. Both players benefit regardless of who performed the clearances, so no player falls behind on upgrades.

Care may dominate when healing can be used efficiently; Guard may dominate with many remaining monster rooms. Early weapon decisions stay relevant because neither perk resets equipment. Neither assumption is measured. A failed run currently offers learning only; whether failure should produce interesting *within-run* recovery before defeat remains open. If growth feels like arithmetic rather than agency, test a single tactical ability instead of adding more tiers.

## Physical and accessibility budget

One deck, two health totals, two visible weapon histories, one active-player indication, one flee flag, one potion flag, and a room count; growth adds an ability name and possibly a per-room checkbox. Use a written name or movable scrap for the active player. Keep spent-potion and flee reminders in text. Card types use suit shapes and names, not color alone. Standard playing-card indices may still be hard to read; ask players before commissioning art.

Setup involves sorting eight cards out of a 52-card deck and shuffling; no measured setup time yet. Arithmetic is subtraction with a zero floor and capped healing. Potential downtime is one partner action plus joint discussion. These are component/rule observations, not measured usability or duration.

## Baseline verification and interpretations — 2026-10-25

Sources checked: [reference implementation's published instructions](https://scoundrel-vanilla.netlify.app/) and [a mirrored copy of the creators' 2011 rules](https://aiscoundrel.com/Scoundrel.pdf). The original host at stfj.net did not load during this check. The reference app itself was not interactively tested.

- The reference's removal recipe yields **44**, whereas a nearby display says 40. Use the recipe: 26 black cards plus 18 red number cards. Treat 40 as an unresolved display discrepancy.
- Its example calls a heart a monster. Use suits' defined roles instead: hearts heal; clubs/spades fight.
- The mirrored original supplies black face-card values, mandatory weapon replacement, and discarding later potions without healing. Its jack subtraction example contains a typo: 11 minus 5 is 6.
- The mirror's weapon wording includes an inconsistent parenthesis about equality. The reference's explicit lower-than example supports **strictly descending** values; use that interpretation.
- Zero-floor damage is explicit in the mirror's worked low-monster example. No negative damage healing.
- The precise final-room procedure is supplied by this adaptation: resolve all remaining cards. Deterministic flee ordering is also an explicit local interpretation.
- Cooperative health, ownership, turn alternation, loss condition, visible discard, and growth are local experiments. Original solo health is 20; the proposed two-player setup is not a verified multiplayer baseline.

## Next decision

First observe whether two people can make meaningful choices with mandatory alternation and no weapon trading. Then compare growth using matched deck orders. Do not add characters, new components, or more upgrades until this core question has evidence.
