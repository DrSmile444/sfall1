List of changes:

## v1.8
+ Added [Sound] section and NumSoundBuffers variable to change the number of simultaneously played sound effects.
+ Added ExtraSaveSlots variable.
+ Added variable NumbersInDialogue to show selection numbers instead of dots in the dialog box.
* The name of the InstanWeaponEquip variable has been corrected to InstantWeaponEquip (as it should have been originally).
* Added EnableHeroAppearanceMod variable.
  ! Fixed a bug where killed characters would freeze when using kill_critter_type.
  ! Added checks to prevent crashes when using scripts with errors (equipping something without having it in your inventory).
* Improved and corrected character control in battle - the character temporarily receives the "Observation" perk (of course, if the main character has it), armor removal when using a script mod has been fixed, the character's name is shown instead of the stealth indicator, karma is calculated correctly when killing enemies, and only the main character receives experience in battle (for example, for a quest).
+ If a weapon has multiple sound effect options for a specific action, the effect is now randomly selected when played.
  ! In FreeWeight, an incorrect visual change in the number of items on exchange tables has been fixed.
  ! Fixed the use of a fixed position to call the start script procedure when there is no standard handler.
  ! Added a fix for using imported procedures with variables (http://teamx.ru/site_arc/smf/index.php-topic=398.0.htm).
  ! Fixed using gdialog_mod_barter with characters without the trade flag set.
+ Added CanSeeAndHearFix variable to enable additional blindness and line-of-sight checks in the is_within_perception_ engine function.
* TurnHighlightContainers now also affects dead characters.
+ The TimeScale variable has been added to the [Speed] section to change (increase) the speed of time in the game.
* Fixed handling of the mood parameter in the start_gdialog function - now it is always taken into account, and can also be equal to -1, in which case the mood is calculated by the engine using a zero local variable from the "talking head" script.
  ! The functionality of the ProcessorIdle variable has been fixed.
- The SkipSizeCheck and ExtraCRC variables have been removed from the [Debugging] section (a different method of checking data integrity is used), as well as Init (important messages are always written to sfall1-log.txt).
  ! Fixed incorrect item counting in the item_count_ engine function.
  ! The "Swing" perk has been fixed.
  ! Several bugs related to battle recording have been fixed.
+ Added the DamageFor mula variable to use the damage formula from F2, taking into account all ammunition parameters (armor-piercing ammo is not the same as semi-jacketed ammo). Modified pro ammunition files or the use of the AmmoFile variable with the corresponding data file are required.
+ Added a new damage calculation formula - Haenlomal's Yet Another Ammo Mod. Requires modified Pro ammo files or the use of the AmmoFile variable with the appropriate data file.
  ! Fixed the loss of additional movement points (from the "Movement Bonus" perk) if all main movement points were used.
  ! Fixed an issue where the saved value of additional movement points (from the "Movement Bonus" perk) was ignored when loading into battle.
  ! The "Silent Death" perk now also applies to critical hits.
+ Added the combat_looks variable, similar to the "Info in battle" setting from F2: enabling it will allow you to assess the health status of another character in battle by hovering the crosshair cursor over them.

## v1.7
* FreeWeight now shows "owning character's free weight/free bag size" for open nested bags.
  ! Several bugs related to the "Take All"/"Put All" buttons (and nested bags) have been fixed.
  ! Fixed an issue where items would disappear from the inventory when attempting to place them in a nested bag if the player was overloaded.
+ The player's equipment screen now shows the "owning character's free weight/free bag size" of an open nested bag.
  ! Fixed the engine's functionality for retrieving equipped armor and weapons from the player's hands if a nested bag is open in the inventory.
  ! Fixed the message being displayed in the monitor window when hitting a random target if it's not a character and has a script.
* When UseScrollWheel=1 you can scroll the monitor window (although not as efficiently as HRP does).
  ! Fixed the use of nested bags in the trade window.
  ! Fixed a potential crash when attempting to open a bag/backpack in the trade window.

## v1.6
* For the FreeWeight variable, we had to change the display format, removing the maximum value. The current format is "free weight" for characters and "free size" for containers.
* Improved fix for the bug "forced use of explosives if the explosion hits someone nearby, returning to the map and then leaving the map again."
  ! Fixed obj_can_hear_obj and slightly tweaked obj_can_see_obj.
* Now, when the UseScrollWheel variable is enabled, you can scroll the target's inventory in the loot box/corpse window or the trade window.

## v1.5
! Fixed a crash bug with explosives.
Fixed a crash bug that occurred when using explosives (throw explosives and leave the map before they explode) if the explosion hits someone nearby, returning to the map, and then leaving again.
! Now, when you force-use explosives and the victim dies, destroy_p_proc is called.
* The value of the SpeedInterfaceCounterAnims variable can be equal to 2 - in this case, the value of the counters will change instantly.
+ Added the InstanWeaponEquip variable, enabling which disables the animation of putting away/taking out weapons when changing them, opening boxes, etc.
+ Added the TimeLimit variable :) The player's age is now displayed correctly on the character screen (however, it is limited to 99 so as not to spoil the output).
+ Added PipboyTimeAnimDelay variable to change the speed of time animation in the Pipboy alarm clock.
+ Added the AnimationsAtOnceLimit variable to increase the number of animations played simultaneously on the map.
  ! Fixed a bug where extra action points were used in combat instead of the specified ones (2 AP) when using an item in hand (5 AP) or using the "Use item from backpack" action icon (3 AP).
  ! Fixed the display of damage received during instant death.

## v1.4
* Added CanSellUsedGeiger variable to control whether the Geiger Counter/Invisible Man can be sold after use.
  ! Fixed the display in the game monitor window of the amount of experience points gained, taking into account the bonus from the "Diligent Student" perk, after killing enemies or stealing.
  ! Fixed the "NPC turns into a container" bug.

## v1.3
+ The NoCredits variable has been added to the [Debugging] section; enabling it disables the display of built-in thanks.
  ! You can now sell the Geiger Counter/Invisible Man after using it.
+ Added the QuestsFile variable to use a file containing information about quests added to the pipboy.

## v1.2
* The BlackSkilldexFix and DodgyDoorsFix variables have been removed from ddraw.ini - these are pure bug fixes, and enabling them permanently does not cause any side effects, so having these variables in the ini file is pointless.
+ Added SaveInCombatFix and SuperStimExploitFix variables.

## v1.1
! Added the BlackSkilldexFix variable to fix the "black and inactive buttons if the Pip-Boy has many quests and holotapes" bug.
! Fixed a bug that caused the game to crash when attempting to move something from a bag/backpack to the player's inventory.

### 03/07/15
! Fixed a bug with displaying negative values (0 will be shown) in the skills window.
+ If the "Bonus Damage at Range" perk is taken, the inventory will show the change in min/max damage for the weapon in your hands.
+ Added BonusHtHDamageFix variable (default = 1) - the effect of the "Melee Damage Bonus" perk is applied not only to the maximum, but also to the minimum damage with a melee weapon/without a weapon.

### 01/07/15
* The DebugMode variable can now be used not only with the debug version of the dll, but also with the release version.
* The ExtraCRC variable can now specify multiple crc options, separated by commas.

### 30/06/15
+ Added the RemoveFriendlyFoe variable, which removes the "Good Enemy" perk, but leaves its effect enabled (in battle, the outlines of party members will be green, like in F2).

### 26/06/15
+ Now you can use the line feed control character (\n) in object descriptions from pro_*.msg files.

### 25/06/15
! Just in case, we've fixed a bug that could cause the game to crash (even though it doesn't happen here) if you tried to kill any character after pumping them full of super stimulants and then leaving the map.

### 24/06/15
* If control (ControlCombat) of party members or all characters in battle is enabled, then the "Stealth" skill cannot be enabled for controlled characters.

### 20/06/15
! Fixed a bug with dependency checking for any characters (previously, player data was always used).

### 17/06/15
+ Added the ControlCombat variable for controlling party members or all characters in combat. The ControlCombatPIDList variable allows you to specify specific characters to control. Player traits/perks do not apply to controlled characters. Controlled characters cannot equip armor in their inventory, cannot save, and pressing Enter (end combat) is recognized as Space (end turn).

### 13/06/15
! The engine's functions for retrieving equipped armor and weapons in hand have been fixed. They lack the required checks, and when called for a non-player, they return equipped armor and a weapon in the player's hand (assuming, of course, that the armor is equipped and the weapon is in the player's hand).

### 06/06/15
+ Added the ColorLOS variable to change the outline color of enemies not within line of sight (LOS). The algorithm is similar to the F2 engine implementation: the "visibility" of LOS enemies is determined by the value of perception * 5. If the enemy has the "transparency" flag set (stealthboy enabled), then the "visibility" is halved - (perception * 5) / 2.

### 30/05/15
+ Added the DontTurnOffSneakIfYouRun variable. If enabled, the Sneak skill will not be disabled when sprinting is enabled and the "Silent Run" perk is not equipped. Instead, the character will walk.

### 29/05/15
+ Added the AutoQuickSave variable for using more than one slot when quick saving (F6) without first selecting a slot. The value determines the number of slots used (1..10) – counting from the first slot, cycling through, overwriting the earliest game.

### 05/25/15
* Fixed original SpeedInterfaceCounterAnims at death (negative values), when, for example, "-993" was shown instead of "-007".
+ Added the EnableMusicInDialogue variable, which can be used to enable music playback when communicating with talking heads. The effect is the same as with non-talking heads - the music volume is halved.
+ Added the MaxPCLevel variable, which can be used to change the maximum player level.

### 16/05/15
+ Added a fix for critical hit table errors and kill ap data. This is what OverrideCriticalTable=2 fixes in the F2 version.

### 11/05/15
+ Changed the distance to step from 5 to 1 when you need to use something on an object, pick it up, clean it, or use a skill on it.
+ Changed the minimum and maximum values when selecting a player's age from 16-35 to 8-60.
+ Added the FakeCombatFix variable to fix cheating with the "A" button – you can pick up items, open containers, and use something on someone if the target is nearby. After an aggressive action (shot/hit/etc.), you can move.

### 10/05/15
+ Added TurnHighlightContainers variable to the [Input] section - turns on/off the highlighting of containers when using ToggleItemHighlightsKey.
* The perk selection window on the character screen has been moved higher.

### 05/05/15
* ToggleItemHighlightsKey functionality has been expanded—it now highlights not only items on the ground but also containers. The highlighting is now in a different color. The highlighting is now aligned with the mouse cursor to eliminate the situation where an item is first highlighted by the mouse cursor, then the hotkey is pressed, released, and the highlighting disappears for the item the mouse cursor is on. To improve visibility, the highlighting color has been changed from yellow to pink when hovering over an item.
+ An unused perk no longer "disappears" after receiving the next perk level (you can accumulate perks).
* Fixed the possibility of getting multi-level perks earlier: for example, do not use a perk at level 9 and at 12 immediately take two levels of the same perk, which in the original can only be taken at levels 12 and 15.

### 02/05/15
+ Added variables NPCsTryToSpendExtraAP, RemoveCriticalTimelimits and PlayIdleAnimOnReload.
+ Added the DrugExploitFix variable to disable the abuse of drug effects when reading books, receiving perks, and increasing skills.
  ! Fixed two clickability bugs in the Pip-Boy.
+ Added hotkeys for the Pip-Boy control buttons - '1' for 'Status', '3' for 'Map', '4' for 'Archives' and '2' for the alarm clock.
  ! Just in case, the "Too Many Items Bug" has been fixed - "if it suddenly becomes impossible to access a map because the game freezes on a black screen" (c).
  Fixed a bug when loading weapons in the inventory: if the weapon is unique and placed in front of the ammo, only one box of ammo is used, even if the maximum number of boxes is specified.
  Fixed a bug affecting weapon loading using the "drag ammo from inventory to weapon in inventory" method when using the High Resolution Patch and the IFACE_BAR_MODE variable from f1_res.ini is set to 1 (the slot number for the item being dragged is incorrect).
+ Added the ability to use Russian when entering the player name and description for saved games. Different localizations use different encodings (Fargus/LevCorp - 866, 1C -1251), so you need to select the appropriate one using the XltTable variable. In-game switching to Russian is performed by pressing the key specified in the XltKey variable (Scroll Lock by default).
+ Added "Drop All" and "Take All" buttons when exchanging with a container. Hotkeys 'd'|'D' and 'a'|'A' can be used. The "Drop Item" and "Take/Use" mouse icons are used to display the buttons.

### 26/04/15
+ Added the FreeWeight variable to display the free weight when trading with containers and during theft or trade (free weight is not shown for the merchant, as he can sell items even if they are underweight). The format is "free weight/maximum weight" for characters and "free volume/maximum volume" for containers.
+ Added the ReloadWeaponKey variable, which assigns a hotkey for reloading a weapon or using an item in the active hand.
+ Added AutoReloadWeapon variable to automatically reload weapons in both hands after the end of the battle.
* Added ReloadReserve variable, which changes the mechanism of reloading weapons by dragging and dropping ammo onto this weapon: -1 = original with an intrusive window for entering the number of packs; 0 = use all available ammo; 1 or more = reserve ammo packs - if the available number of ammo packs is greater than the specified reserve, then all ammo minus the reserve will be used, if less than or equal to the reserve, then only one pack of ammo will be used.
+ Added the StackEmptyWeapons variable for stacking identical weapons without ammo - solves the problem of two weapon stacks after unloading the same weapon, but with different ammo.
+ Now, when you open your inventory, you can drag and drop stimpacks and other chemicals from your inventory onto the player's image with the use effect.

### 23/04/15
+ Added variables ToggleItemHighlightsKey, DisplayKarmaChanges and DebugMode.

### 22/04/15
+ Added several variables from sfall2, like StartingMap, VersionString, etc.
  ! The source code for v1.14a of the original sfall for Fallout 1 was used for compilation.
