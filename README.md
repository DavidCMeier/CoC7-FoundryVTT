# My Call of Cthulhu implementation for Foundry VTT

My implementation of the call of Cthulhu for foundry-vtt  

## Disclaimer

This system doesn’t include any materials from the books and you’ll have to enter manually, weapons, skills, items etc… to be able to play.
I’ve just provided some basics skills that you can use.

I’m testing my dev on Chrome. Not sure how or if it will behave on other browser.

## Installation/usage

Install in foundry VTT from the Game Systems tab using the following manifest :  
<https://raw.githubusercontent.com/HavlockV/CoC7-FoundryVTT/master/system.json>  

Compendium 'Examples' contains a 1920's character sheet, you just need to import it to start a character. Contains also a NPC and a creature example.  
Compendium 'Skills' contains a set of basic skills that you can use for your PC/NPC.  
Compendium 'Weapons' contains a single test weapon.  

## What is working

version 0.3.1 :

* Templates for books and spells added.
  * You can add a spell to a book by dragging it (from item directory only for the time beeing) on the book.
* Bug fix, luck amount spent is now correctly displayed on the roll result.
* Japanese translation improved thanks to AdmiralNyar

version 0.3.0 :

* Hot fix on luck spent.

version 0.2.9 :

* Bug fix forcing a fail or a pass should work as intended.
  * Doing so will show a fail or a pass to the player.
* Bug fix, a combat roll will now flag the skill for experience correctly.
* You can now 'cheat' bu modifying the success level of the rolls before revealing the (blind rolls only)
  * On blind rolls you have 2 new buttons for the keeper use only: increase/decrease success.
  * Once your happy with the result push reveal check.
  * Experience will not be flagged, keeper needs to manually award it with the corresponding button.
* On blind roll, the level of success will not be revealed until you push reveal check button.
  * Pushing force fail/pass will just indicate to the player the failure or the success with no level indication.

version 0.2.8 :

* Bug fix/improvement on melee flow cards.
  * Synthetic actors and token are retrieved from the viewed scene (use to be from active scene).
  * Actors and target retrieval hardened.
  * Flow simplification (Resolution card is replaced after resolution).
* Rolls received a lot of work.
  * Success level is displayed as medals (critical), stars (success), spiders (failure) or skull (fumble).
  * Addition of unknown difficulty rolls.
    * Selection of difficulty is done in the roll dialogue. Select the '???' options.
    * Default mode (unknown difficulty or normal difficulty) can be selected in the world options.
    * Player rolling can see his numbers but not the check difficulty. He can spend luck to improve his success.
    * Roll difficulty and success level is revealed upon difficulty selection by the keeper.
  * Unknown difficulty check can be rolled as normal check (public, private and blind).
* ただいま#0125 Dicebot module has been integrated and will be supported in the system.
  * Type commands /cc and /cbr to use it.
  * /cc xx will roll a D100 vs a xxx difficulty and display the level of success.
  * /cbr xx, yy will roll a D100 vs xx and yy difficulty and display the level of success.
* Japanese translation improved and augmented thanks to ただいま#0125!
* Localization continues thanks to the efforts of Kael79#8036.
* French translation improved and augmented thanks to Kael79#8036.
* French discord community is helping with debugging and testing (special thanks to Carter#2703 and Drakenvar#8665).
* Tutorial videos are on the way !

version 0.2.7 :

* Bug fix/improvement on melee flow cards.
  * Addition of portraits on cards.
  * Double click on chatcard icons will open corresponding actor.
* Implementation of blind and private GM rolls.
  * Keeper has the possibility to force the check to pass or to fail.
  * Keeper has the possibility to reveal the check result.
  * Awarding experience automatically is disabled for blind check. Keeper can award experience.

version 0.2.6 :

* Modification of rolls and dice to be compatible with 0.7.x.
  * 0.7.x bring a lot of changes. __This needs more testing. I *strongly* recommend to wait before upgrading to 0.7.x__

version 0.2.5 :

* Bug correction on creature sheets.
  * Size is now limited and content will be scrolled.
  * Weapon damage is now correctly entered.
  * Added a small reminder for bonus damage after weapons damage formula

version 0.2.4 :

* Range combat supports shotguns.
* Bug correction (spending luck on luck and SAN rolls no more possible).
* Slight range combat refactoring (more to come at a later stage. Aim is to reduce size and number of cards).
  * Additions of icons to the cards.
  * Bonus, penalties, target response have been moved to the card tooltip once the card is resolved.
* Spanish translation updated thanks to Gerbek.

version 0.2.3 :

* Hotfix.

version 0.2.2 :

* PDFoundry Integration.
* First implementation of range combat.
  * Weapon sheet has been modified.
  * select a target (or not) and in the combat tab click on a range weapon name. This will start the range combat flow and open a range combat chat-card.
  * All bonus and penalties can be overridden by the keeper only.
  * Range and difficulty are automatically calculated.
  * Bonus for target size, speed are automatically applied.
  * Bonus for shooting at point blank is automatically given.
  * Calculation of bullets wasted when switching target in automatic fire mode.
  * Penalty dice for multi/auto fire are applied.
  * Difficulty automatically increased with mode than 2 penalty dice.
  * If you don't have a target a fake 'dummy' target will be created.
  * Supports auto-fire, burst, single shot, multi shots.
  * Supports weapon malfunction.
  * Damage rolls (armor is not taken in account).
  * What is coming next:
    * Implementation of shotgun type weapons and explosives.
    * Distribution of damage to the targets and status applied.
    * Attribution of malfunction to the corresponding weapons.
    * Implementation of fast forwarding for range and melee combat.
    * Implementation of bullets.
    * Limitation on number of shot fired (depending on the weapon max shot per rounds and bullets in the magazine).
* Support for Japanese translation thanks to AdmiralNyar.
* Bugs correction
  * Movement calculation.

version 0.2.1 :

* Template and CSS correction.

version 0.2.0 :

* Implementation of experience tracking.
  * A successful (no bonus, not pushed, no luck used) check will flag a skill for development. A skill flagged for development will show a gold star next to it’s score. You can flag or un-flag a skill by double clicking on the corresponding star in the skill tab.
  * Addition of a new skill property 'No XP gain'. Set to false by default. A skill with this property enabled will not benefit from experience tracking.
  * Unlock the character sheet to access the 'Development phase' button. Clicking it will roll experience and increase all skills accordingly.
* Implementation of cash and assets under the Gear & Cash tab. Spending level, Cash ans Assets are calculated automatically according to 1920’s CoC rule book.
  * Unlock the character sheet to allow modification of the calculations.
  * Clicking the cog will toggle between manual and automatic modes.
    * In manual mode (gray cog), just enter whatever you feel like in the fields.
    * In automatic mode (green cog), you can change the monetary symbol and factor. By default the system uses $ and a factor of 1. The factor will just multiplies all values. Enter 20 for modern CoC for example.
  * Addition of a spent counter. It is to track cash spent today and check it against the available cash.
  * Addition of an 'Assets details' section.
  * Addition of a 'Notes' section.
* Implementation of backstory tab. Some backstory element are proposed with the default 1920’s character sheet.
  * Unlocking the character sheet will allow you to:
    * add a new section (Add section button).
    * change section names.
    * delete a section (Trash icon next to the section name).
    * change sections order (Up and Down arrows next to the section name).
* Addition of daily sanity loss counter and reset counter button.
  * Upon changing sanity all losses will be recorded.
  * Loosing 5 points at once or loosing more than 1/5 of current sanity will lit the according status (Indefinite insanity, temporary insanity).
  * Clicking on the reset button next to the counter will reset it to 0.
* Improvment of the combat tab.
  * Melee and range weapon are shown in different sections
  * The combat skill will show at the bottom of the combat section.
  * Unlock the sheet to allow modifications of skills and weapons.
* Addition of calculation of average values for characteristics of creatures and NPC.
  * Unlock the creature/NPC sheet, pass the sheet in 'values' mode (icon next to the lock should display a small person with a pen).
    * The red dices will roll characteristics when a formula is available.
    * The red scale will average characteristics values when a formula is available.
  * In 'formula' (icon next to the lock should display a small square-root symbol) you can now reference other characteristics (Enter @POW for example to set that characteristic to the same value as POW).

version 0.1.9 :

* Rework of the close combat mechanism. Select a target click on the weapon name and select the different options on the chat cards.
* Implementation of damage bonus on weapon damage roll.
* You can now override the auto calculation of max HP and MP for PC. Click the lock to edit the sheet, there will be a green cog next to max HP and MP. Clicking it will toggle between manual and auto calculation of max HP/MP.
* Typo corrections.
* German translation, thanks to MrViso.

version 0.1.8 :

* Started to implement the combat mechanisms (close combat only).
  * You can select one or many targets and click on a weapon name in the combat tab/section.
  this will open a roll window where you can roll the attack, select if you're outnumbered and choose options for defense (dodge/fight back/maneuver).
  When all participants have rolled, the card will show the results and propose to roll the damage.
  * You will see the corresponding option (roll attack or defense) only if you are the owner. Result will be public.
  * If you have enough, you can spend luck to pass a failed check. This will update the result card. Spending luck to increment your success is not implemented yet.
  * Now working on improving/debugging the flow before implementing attack maneuver (trample for example) before moving to range weapon attack.
* Addition of a small cog next to attributes in NPC/Creature sheets. Clicking it will toggle the attribute to auto calculation (green cog) or manual input (gray cog).
* Creatures are now created with a fighting skill and a natural attack. This will be extended soon to PC/NPC sheets.
* Added the lock mechanism to the PC sheet.
* Added the add skill/weapon/item to the PC sheet.
* Be aware this is an 'experimental' increment, template had to be modified. I did my best but I can't assure that previously created entities will work.

version 0.1.7 :

* Added a lock switch to allow editing of NPC/Creature sheet
  * When locked you still can modify some of the sheet numbers by double clicking on them.
  * Unlocking the sheet will allow more advanced modifications and additions of entities.
* You can add skills/items directly from NPC/Creature sheet, without the need to pull them from compendium or items.
  * Upon clicking the + sign the corresponding entity will be created and the corresponding entity sheet will open.
  * Holding shift while clicking the + sign will not open the sheet just create a generic entity.
* Creatures have a formula button, allowing to enter formulas instead of characteristics.
  * Formulas need to be valid roll strings (like the /r command).
* Starting to implement localization.  

version 0.1.6 (07/06):

* Lock mechanism to avoid inadvertent actor modification (NPC only so far).  
* Implementation of basic NPC sheet.
* Using basic NPC sheet for creature.
* Bug correction:
  * You can add many time the same weapon or item, not twice the same skill with the same name.

Version 0.1.5 (01/06) :  

* Luck and San roll implemented.  
* Start implementing NPC sheet with only attributes and skills.  
* Mention of eras in skills removed. It is much simpler to just create a character sheet template and a compendium for each setting.
* Attributes (HP, MP, San, Luck) values can bet set using the mouse-wheel.
* Bug correction:
  * Parasite (future) windows during skill roll removed.  

Version 0.1.4 (31/05) :

* You can spend luck (providing you have enough) to pass a failed check.  
* You can push a skill if it is 'pushable' (pushed enabled on the skill sheet).  
* Typo correction.  

Version 0.1.3 :  

* The character sheet.  
  * You can enter your characteristics. Entering them will update the attributes (max HP, MP …).  
  * If a field is not editable it’s because it’s locked (black border). Double clicking on it will unlock it (red border, this is to prevent inadvertent modifications).  
  * Manually modifying an automatic field  (like max HP) will remove the auto calculation. To reset it, set it to -1.  
* You can roll skills from the sheet by clicking the icon.  
* You can roll your weapons from the combat tab. If the weapon is tagged as ‘Full-Auto’ you will see 2 clickable zones reflecting the 2 different skills used in normal and auto mode.  
  * If the background is red, that’s because no skill have been attached to that weapon, edit the weapon to assign a skill to roll.  
* You can roll a characteristics by clicking his name
* Clicking the icon/name will perform and advanced roll (dialogue selection for penalty/bonus and difficulty).  
* Holding shift while clicking will roll the dice with no penalty vs regular difficulty.  

## Future plans

* [ ] Correcting bugs.  
* [x] Implement luck rolls.
* [x] Implement Creatures (with automatic and average carac/skill calculation).
* [x] Implement NPC (with automatic and average carac/skill calculation).
* [x] Implement creations of skills directly from the sheets.
* [x] Implement experience tracking.
* [x] !!WIP. Implement localization.
* [ ] Working on CSS/HTML to improve the look.  
* [x] Improving the combat tab, by adding combat skill to the weapon list.  
* [ ] Automatic skill assignment when adding a weapon.  
* [ ] Combat automation (calculation of difficulty, assignement of damage, opposed check...).  
* [x] Implement pushed rolls.  
* [ ] Implement advanced rolls (opposed, combined etc…).  
* [ ] Implement car chases.  
* [ ] Automation of character creation.
