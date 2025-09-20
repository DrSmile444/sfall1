# Changelog

> Legend: **Added**, **Changed**, **Fixed**, **Removed**  
> Variables, functions, sections, and constants are formatted as code (e.g., `NumSoundBuffers`, `[Sound]`, `start_gdialog`).

---

## v1.8

### Added
- `[Sound]` section and `NumSoundBuffers` to configure the number of simultaneously played SFX.
- `ExtraSaveSlots`.
- `NumbersInDialogue` to show selection numbers instead of dots in the dialog box.
- `EnableHeroAppearanceMod`.
- Randomized selection for weapon SFX variants when multiple are available for the same action.
- `CanSeeAndHearFix` to enable additional blindness and LOS checks in the `is_within_perception_` engine function.
- `TimeScale` under `[Speed]` to increase in-game time speed.
- `DamageFormula` option to use Fallout 2’s damage formula considering all ammo parameters (requires modified Pro ammo files or `AmmoFile` with matching data).
- New damage formula: **Haenlomal’s Yet Another Ammo Mod** (requires modified Pro ammo files or `AmmoFile` with matching data).
- `combat_looks`, similar to F2’s “Info in battle” — hover the crosshair to assess a target’s health in combat.

### Changed / Improved
- Renamed `InstanWeaponEquip` → `InstantWeaponEquip` (originally intended name).
- Combat control improvements:
  - Temporarily grants the “Observation” perk to the controlled character (if the main character has it).
  - Fixed armor removal when using script mods.
  - Shows the character’s name instead of the stealth indicator.
  - Correct karma calculation for enemy kills.
  - Only the main character receives quest-related XP in combat.
- `TurnHighlightContainers` now also affects dead characters.
- `start_gdialog` mood handling: mood is always respected; can be `-1` to let the engine compute via the zero local variable from the talking head script.

### Fixed
- Frozen killed characters when using `kill_critter_type`.
- Crash prevention when scripts attempt invalid actions (e.g., equipping items not in inventory).
- Incorrect visual count changes on exchange tables in **FreeWeight**.
- Using a fixed position to call the `start` script procedure when no standard handler is present.
- Imported procedures with variables (see reference: <http://teamx.ru/site_arc/smf/index.php-topic=398.0.htm>).
- `gdialog_mod_barter` with NPCs lacking the trade flag.
- `ProcessorIdle` functionality.
- Incorrect item counting in the `item_count_` engine function.
- “Swing” perk behavior.
- Multiple battle recording bugs.
- Loss/restore logic for extra movement points from “Movement Bonus” perk (both on use and when loading into battle).
- “Silent Death” now also applies to critical hits.

### Removed
- From `[Debugging]`: `SkipSizeCheck` and `ExtraCRC` (new data integrity method used), and `Init` (important messages are always logged to `sfall1-log.txt`).

---

## v1.7

### Added / Changed
- **FreeWeight** now shows “owning character’s free weight/free bag size” for open nested bags.
- Player equipment screen shows “owning character’s free weight/free bag size” for an open nested bag.
- When `UseScrollWheel=1`, you can scroll the monitor window (less efficient than HRP).

### Fixed
- Several issues with **Take All**/**Put All** buttons (including nested bags).
- Items disappearing when placing them into a nested bag while overloaded.
- Engine behavior retrieving equipped armor/weapons when a nested bag is open in the inventory.
- Monitor window message when hitting a random target that isn’t a character but has a script.
- Nested bag usage in the trade window.
- Potential crash when opening a bag/backpack in the trade window.

---

## v1.6

### Changed
- **FreeWeight** display format changed: removed the max value.  
  Now: “free weight” for characters, “free size” for containers.

### Fixed
- Improved fix for forced explosive use if an explosion hits someone nearby, then returning to the map and leaving again.
- `obj_can_hear_obj` fixed; minor tweaks to `obj_can_see_obj`.

### Added
- With `UseScrollWheel=1`, scroll target’s inventory in loot/corpse window and trade window.

---

## v1.5

### Fixed
- Crash bugs with explosives (including the sequence: throw → leave map pre-explosion → explosion hits someone → return → leave again).
- On forced explosive use where the victim dies, `destroy_p_proc` is now called.
- Incorrect usage of extra AP in combat when using hand items or “Use item from backpack” action icon.
- Display of damage received during instant death.

### Changed
- `SpeedInterfaceCounterAnims` can be `2` for instant counter value updates.

### Added
- `InstanWeaponEquip` (disables put away/take out animations when switching weapons, opening boxes, etc.).
- `TimeLimit` (player age displays correctly on the character screen; capped at 99).
- `PipboyTimeAnimDelay` to adjust the Pip-Boy alarm clock animation speed.
- `AnimationsAtOnceLimit` to increase the number of simultaneous map animations.

---

## v1.4

### Added
- `CanSellUsedGeiger` to control whether the Geiger Counter/Invisible Man can be sold after use.

### Fixed
- Monitor window XP display accounting for the “Diligent Student” perk after kills/steals.
- “NPC turns into a container” bug.

---

## v1.3

### Added
- `NoCredits` in `[Debugging]` to disable built-in credits.
- `QuestsFile` to supply a file with Pip-Boy quest info.

### Fixed
- Geiger Counter/Invisible Man can be sold after use.

---

## v1.2

### Removed
- `BlackSkilldexFix` and `DodgyDoorsFix` from `ddraw.ini` (pure bugfixes enabled permanently).

### Added
- `SaveInCombatFix` and `SuperStimExploitFix`.

---

## v1.1

### Added / Fixed
- `BlackSkilldexFix` to address “black/inactive buttons when Pip-Boy has many quests/holotapes.”
- Crash when moving items from bag/backpack to player inventory.

---

## 2015-07-03

### Fixed
- Negative value display in the skills window (now shows `0`).

### Added
- If “Bonus Damage at Range” perk is taken, inventory shows min/max damage changes for the weapon in hand.
- `BonusHtHDamageFix` (default `1`): “Melee Damage Bonus” applies to both min and max for melee/unarmed.

---

## 2015-07-01

### Changed
- `DebugMode` now usable with both debug and release DLL builds.
- `ExtraCRC` now accepts multiple CRCs separated by commas.

---

## 2015-06-30

### Added
- `RemoveFriendlyFoe`: removes the “Good Enemy” perk but keeps its effect (party outlines green in combat, like F2).

---

## 2015-06-26

### Added
- Support for `\n` line feeds in object descriptions from `pro_*.msg`.

---

## 2015-06-25

### Fixed
- Potential crash when trying to kill a character after stacking them with super stims and then leaving the map.

---

## 2015-06-24

### Changed
- When `ControlCombat` is enabled for party/all characters, “Stealth” cannot be enabled for controlled characters.

---

## 2015-06-20

### Fixed
- Dependency checking for arbitrary characters (previously always used player data).

---

## 2015-06-17

### Added
- `ControlCombat` to control party members or all characters in combat.  
  Use `ControlCombatPIDList` to target specific PIDs.
  - Player traits/perks don’t apply to controlled characters.
  - Controlled characters cannot equip armor in their inventory and cannot save.
  - Pressing **Enter** (end combat) is treated as **Space** (end turn).

---

## 2015-06-13

### Fixed
- Engine functions retrieving equipped armor and weapons in hand lacked required checks; when called for non-player, they returned the player’s gear.

---

## 2015-06-06

### Added
- `ColorLOS` to change outline color of enemies not within line of sight.  
  Visibility is `PER * 5`; halved if enemy has “transparency” (stealthboy).

---

## 2015-05-30

### Added
- `DontTurnOffSneakIfYouRun`: with sprinting and without “Silent Run,” Sneak won’t toggle off — character walks instead.

---

## 2015-05-29

### Added
- `AutoQuickSave`: rotate through multiple quick-save slots (`1..10`), cycling and overwriting the oldest.

---

## 2015-05-25

### Fixed
- Original `SpeedInterfaceCounterAnims` at death (negative values like `-993` instead of `-007`).
- Two Pip-Boy clickability bugs.
- “Too Many Items” black-screen freeze on map access.
- Weapon loading quirks with unique weapons placed before ammo (only one box used even when more allowed).
- Weapon loading via drag-and-drop with HRP and `IFACE_BAR_MODE=1` (incorrect dragged item slot).

### Added
- `EnableMusicInDialogue`: enable music with talking heads; volume halves (like non-talking heads).
- `MaxPCLevel` to change max player level.
- Russian input for player name and savegame description.  
  Select encoding via `XltTable` (e.g., Fargus/LevCorp 866, 1C 1251) and toggle in-game with `XltKey` (default: Scroll Lock).
- “Drop All” and “Take All” buttons when exchanging with containers (`d`/`D`, `a`/`A` hotkeys).  
  Uses “Drop Item” and “Take/Use” mouse icons.

---

## 2015-05-16

### Added
- Fix for critical hit table and `kill_ap` data (equivalent to `OverrideCriticalTable=2` in F2).

---

## 2015-05-11

### Added
- Step distance changed from `5` to `1` for use/pick/clean/skill actions on objects.
- Player age selection range changed from `16–35` to `8–60`.
- `FakeCombatFix`: prevents “A-button” abuse (pick items, open containers, use on targets nearby). Movement allowed after aggressive action.

---

## 2015-05-10

### Added
- `TurnHighlightContainers` in `[Input]` to toggle container highlighting with `ToggleItemHighlightsKey`.

### Changed
- Perk selection window on the character screen moved higher.

---

## 2015-05-05

### Changed
- `ToggleItemHighlightsKey` now also highlights containers (different color), tracks mouse-hovered item to avoid highlight flicker, and changes hover color from yellow to pink.
- Unused perk no longer disappears after gaining the next perk level (perks can accumulate).
- Prevents early acquisition of multi-level perks (e.g., skipping at level 9 then taking two at 12 when original allows only at 12 and 15).

---

## 2015-05-02

### Added
- `NPCsTryToSpendExtraAP`, `RemoveCriticalTimelimits`, `PlayIdleAnimOnReload`.
- `DrugExploitFix` to disable exploits when reading books, gaining perks, and increasing skills.
- Pip-Boy hotkeys: `1` = Status, `3` = Map, `4` = Archives, `2` = Alarm Clock.

### Fixed
- Two Pip-Boy clickability issues.
- Weapon loading (inventory drag-to-weapon) issues with HRP and `IFACE_BAR_MODE=1`.

### Changed
- Loading unique weapons placed before ammo now respects maximum box count.

### Added
- Drag-and-drop stimpacks/chems onto the player image from inventory (use effect).

---

## 2015-04-26

### Added
- `FreeWeight` to display free weight when trading with containers and during theft or trade.  
  Format:
  - Characters: `free weight / maximum weight`
  - Containers: `free volume / maximum volume`  
    (Merchants can sell regardless of underweight; their free weight isn’t shown.)
- `ReloadWeaponKey` hotkey for reloading or using item in active hand.
- `AutoReloadWeapon` to reload weapons in both hands after combat.
- `ReloadReserve` to change reload behavior:
  - `-1` = original (prompt for number of packs),
  - `0` = use all available ammo,
  - `>=1` = reserve packs; if available > reserve → use all minus reserve, else use one pack.
- `StackEmptyWeapons` to stack identical weapons without ammo (solves split stacks after unloading).

### Added (QoL)
- In inventory, you can drag stimpaks/chems onto the player to use them.

---

## 2015-04-23

### Added
- `ToggleItemHighlightsKey`, `DisplayKarmaChanges`, `DebugMode`.

---

## 2015-04-22

### Added
- Several variables ported from sfall2 (e.g., `StartingMap`, `VersionString`, etc.).  
  **Note:** Compiled from the original Fallout 1 sfall v1.14a sources.
