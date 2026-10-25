# 001 — constructed rules walkthroughs

Date: 2026-10-25. Rules: 0.1.0-base and 0.1.0-growth. Two players. Method: desk walkthroughs of authored states against the written rules; no physical players, random seeds, simulator, or full-game outcomes. These checks concern resolution, not balance or fun.

## Question

Can the proposed rules resolve ordinary cooperation and key boundary cases without a referee inventing a ruling?

## Authored checks and results

1. **Opening cooperation and alternation (base).** Alex and Bea start at 12, Alex active. Room: 5♦, 9♣, 6♥, K♠. Alex equips 5♦; Bea fights 9♣ barehanded, reaching 3; Alex uses 6♥ on Bea, reaching 9. Three actions resolved; K♠ carries. Both survive, first clearance counted, Bea starts the next room. Observed consequence: equipping Alex leaves Bea exposed, but Alex can heal her. Team health is 21.
2. **Strict limit and replacement (base, independent state).** Alex has 12 health and a fresh 5♦. A 9♣ costs 4, leaving 8 and a limit of 9. Another 9 is ineligible for weapon use. Fighting it barehanded would be lethal; this legal action loses immediately. In a separate continuation from the 8-health state, an 8♠ costs 3, leaves 5, and sets the limit to 8. A subsequent 2-monster costs zero but sets the limit to 2. Replacing the diamond discards its stack and removes the limit. These are separate branches, not one sequence of player turns.
3. **Potion cap and waste (base, independent state).** Bea at 7 receives 6♥ and reaches 12; 1 healing wasted. A second heart in the same room gives zero healing to either player and consumes an action. A first heart selected at full health similarly wastes its healing and spends the allowance. A heart carried untouched into a new room remains usable there.
4. **Flee timing (base, independent state).** Four room cards plus at least one hidden card, previous entry faced: unanimous flee is legal. Bottoming all four and dealing four keeps the total card count unchanged. The active player stays active and cannot flee the replacement room. Facing and clearing it re-enables fleeing at the following eligible entry. Neither a partial room nor an empty-dungeon entry can be fled.
5. **Terminal timing (base, independent state).** Empty dungeon; final room is 2♣ and 3♥. Alex at 2 with no weapon selects 2♣: health reaches zero, immediate team defeat, no potion rescue. In a separate state, Alex starts at 3, survives the same monster at 1, then Bea's action can use 3♥ to heal Alex to 4; empty room means victory. With four cards in a terminal room, resolve all four rather than stopping after three.
6. **Growth unlock (growth, independent state).** Three full clearances recorded; survive a fourth three-action room. Unlock exactly one ability before refill. Choosing Guard makes the first monster next room, 7♣ versus a fresh 5♦, cost 1 instead of 2; the weapon limit becomes 7. A later monster gets no Guard reduction. If the first monster would cost zero, Guard is still spent. Care instead makes a first 3♥ restore 5, capped at 12; a second heart still restores zero. A flee earns no clearance and no unlock. Victory or defeat resets the ability.

Result: these six authored cases have determinate outcomes under the current text. No full shuffle was played. They cannot reveal actual win rate, upgrade dominance, or human ease of use.

## Structural checks

- Card accounting: 52 minus six red faces minus two red aces = 44; 26 monsters + 9 weapons + 9 potions = 44.
- Every resolved card leaves the room for a discard or personal weapon area; fleeing moves cards without duplicating/removing them. Replacing equipment moves its existing cards to discard.
- In a complete surviving run, all 44 cards are selected exactly once. Alternation gives 22 selections each. If no early defeat, there are 14 ordinary three-card clearances and a terminal two-card room. Fleeing changes order, not these counts. Thus the growth trigger is reachable and occurs well before the end.
- Each flee must be followed by resolving cards, so there is no unlimited flee-only stall. These are reasoning checks, not an executable engine validation.

## Findings and limitations

Targeted healing creates an explicit helping action, and weapon ownership creates an allocation constraint. These are available choices, not evidence players will enjoy them. Alternation can force an unarmed player to absorb a large monster. Zero-health defeat is severe; its frequency is unknown. The shared ability adds a choice but primarily changes arithmetic; its experiential value is untested.

No confidence intervals or win-rate estimate apply: there is no sampled game population. Duration, discussion time, and setup time have not been measured.

## Next experiment: human core test, then growth comparison

Play one complete base run with two people first. Record starting deck order privately before play, revealing none of it to players, and preserve the action trace. Log health lost, effective/wasted healing, monsters fought by each player, discarded unused potions, flee count, and final state. Note any ambiguous action before resolving it; change rules only for the next version.

Separately record players' experience, actual setup/run duration, rules questions, confusion, downtime, perceived fairness, memorable decisions, whether anyone dictated the other's actions, and verbatim feedback. Keep observed behavior separate from interpretation. Ask whether either player wanted weapon transfer or a recovery rule.

After clarity issues are fixed, compare base with growth over recorded matched deck orders, tracking Care versus Guard selection and actual benefit. Repeated decks introduce learning; counterbalance order across groups and report that limitation. Human reports must establish usability and fun. A lightweight seeded simulator is the next tool only when repeated games will answer a specific balance question; it has not been built or run here.
