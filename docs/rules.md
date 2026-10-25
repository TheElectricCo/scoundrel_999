# Canonical rules — experimental 0.1.0

Inspired by Scoundrel by Zach Gage and Kurt Bieg. These are original instructions for a proposed cooperative adaptation, not official Scoundrel rules. See [source notes and design rationale](design.md).

Ruleset IDs: **0.1.0-base** uses sections 1–8; **0.1.0-growth** also uses section 9. These are testable proposals. Neither has established balance. Only two-player play is specified.

## 1. Goal and components

Two adventurers explore one dungeon. Both must survive until every dungeon and room card has been resolved. Either adventurer reaching zero health immediately loses the run for the team, including on the final card.

Use a standard deck, paper, and a pencil. Set aside jokers, the J/Q/K of hearts and diamonds, and the two red aces. Check the remaining **44 cards**: 26 monsters (clubs and spades, 2–ace), nine weapons (diamonds, 2–10), and nine potions (hearts, 2–10). Black J/Q/K/A have values 11/12/13/14. Other values match their numbers.

## 2. Setup and information

Each player starts with **12 health**, maximum 12, and no weapon. Choose the first active player by agreement. Record both health totals, whose action is next, whether the last room was fled, and the number of full rooms cleared (initially zero). Shuffle the dungeon face down. Deal four cards face up into the room.

Keep a shared face-up discard pile, each player's weapon and its defeated monsters, and the room visible. Players may inspect these and count remaining cards, but may not look at or reorder the hidden dungeon. Discuss plans freely; the active player decides their own action. There are no secret hands.

## 3. Entering and leaving rooms

Before resolving any card, the active player chooses whether to face the room or proposes fleeing under section 7. Facing commits the team to resolving three cards in any order, one action at a time. Players alternate after **each resolved card**, across room boundaries. A flee does not change the active player.

After three resolutions, leave the fourth card in place, increase full rooms cleared by one, then deal from the top until the room contains four cards or the dungeon is empty. Reset the room's potion allowance. The next player starts the new room. There is no extra action or player switch for entering a room.

**Final room:** whenever the dungeon is empty at entry, resolve every card in that room, even if there are four. Do not carry a card into another room. This final room cannot be fled. If both players remain above zero after its last resolution, win immediately. Empty dungeon and empty room also means victory; defeat takes priority if either health is zero. No refill happens during a room.

## 4. A player's action and ownership

The active player selects exactly one room card and resolves its type. No passing, free discarding, stockpiling, or taking extra actions. Monsters attack the active player only. A selected weapon equips the active player only. A usable potion can heal either player, chosen by the active player; the recipient may refuse, in which case it is discarded without healing and still uses the room allowance.

Health and weapons are individual. The dungeon, room, discard, flee decision, and growth ability are shared. Equipped weapons cannot be lent or transferred; damage cannot be split or redirected. There are no rewards or currency in the base rules.

## 5. Weapons and combat

Selecting a diamond replaces your weapon. Discard the previous weapon and all monsters stacked on it. Place the new weapon in front of you with no monsters on it.

When selecting a monster, choose barehanded combat or your own eligible weapon. Barehanded combat costs the monster's value in health; discard that monster and leave your weapon history unchanged.

A fresh weapon can fight any monster. After it fights one, it can fight only a monster **strictly lower** than its most recently defeated monster. Equal values are ineligible. Weapon combat costs `max(0, monster value − weapon value)` health. Stack the monster on the weapon, leaving the weapon value and latest monster visible. Even a zero-damage fight changes that limit. Weapons never disappear merely because they have become difficult to use.

Resolve damage, with health stopping at zero, then check defeat before any other action. A player cannot wait at zero for a potion; there is no incapacitated state, resurrection, or individual elimination followed by continued play.

Example: your 5-diamond weapon fights a 9-club monster, costing 4 health. An 8-spade is now eligible; another 9 is not. Fighting a 10 barehanded does not change the weapon's limit of 9. Equipping a new diamond resets its history.

## 6. Potions

Only the **first heart selected in a room** can heal. It restores its value to either player, capped at that player's maximum. Discard it. Selecting it at full health, or refusing its healing, still consumes this allowance. Every later heart selected in that room is discarded with no healing. Each selection still costs an action and switches the active player. Potions cannot be saved. A carried heart does not consume the next room's allowance until selected there.

Example: Bea has 7 health and Alex selects a 6-heart to heal her. Bea reaches 12, so 1 point is wasted. A subsequent heart in that room heals nobody, even if Alex is injured.

## 7. Fleeing

Fleeing requires both players' agreement, a four-card room with at least one card still in the hidden dungeon, and no flee on the previous room entry. If agreement fails, face the room. Once any card has been resolved, fleeing is unavailable.

Move the entire room to the bottom of the dungeon in its existing left-to-right order, leftmost first. Deal four new cards. Mark that a flee occurred; the new room must be faced. Fleeing does not consume a player action, clear a room, grant growth, or restore anything. Once a room is resolved normally, fleeing is available at the following eligible entry. The finite deck and mandatory facing between flees prevent indefinite avoidance without progress.

## 8. Timing and end of run

All actions are sequential; no simultaneous actions or reactions exist. Finish the selected card, check defeat, then switch the active player. A surviving final-card action then wins the game. At a normal room end, count the clearance, apply any growth unlock, and refill. Values tied for weapon eligibility fail the strict comparison; ties in planning are settled by the active player, except fleeing needs agreement.

Record victory/defeat, rooms cleared, both final health totals, and anything confusing. All health, equipment, room counts, and abilities reset next run. No points are earned or spent between sessions, including after failure.

## 9. Optional within-session growth — 0.1.0-growth only

**Earn:** immediately after surviving the fourth full room clearance, before the refill, unlock one shared ability. This happens once. Final-room completion never grants an ability because the run has ended. Flees never count toward the four rooms.

**Choose:** the team selects one ability together; if agreement fails, the player whose action is next chooses. Write its name on the health sheet. There is no currency, shopping, or additional upgrade tier.

| Ability | Effect for every subsequent room |
| --- | --- |
| Care | The room's healing potion restores 2 extra health, still capped at 12. No other heart can heal. |
| Guard | Reduce the damage from the first selected monster in the room by 1, minimum zero, whether fought barehanded or with a weapon. This is consumed even if that fight would already deal zero damage. |

**Track:** with Guard, write an empty box at each room entry and check it when the first monster is selected. Care uses the ordinary potion allowance. Fleeing grants no benefit itself; the replacement room starts with its normal allowances. No ability changes weapon eligibility, action order, or the defeat check.

Example: after the fourth clearance, choose Guard. In the next room, a 7-monster against a fresh 5-weapon normally deals 2; Guard makes it 1. The next monster that room gets no reduction. Care would instead turn a 3-heart into 5 healing.

**Persistence:** the chosen ability lasts for the rest of this run and is lost on victory or defeat. Failure grants no mechanical carryover. This deliberately tests one mid-run choice before considering further growth.
