# Wondible's One Hour One Life Client

[Patch Respository](https://github.com/JustinLove/onelife-client-patches) [Patch descriptions](README.patches.md)

## Requirements

Requires a installation of [One Hour One Life](https://onehouronelife.com/), or a derivitive such as [Two Hours One Life](https://twohoursonelife.com/). The mod installs *additional* files into the base installation.

## Installation

[Windows Client](https://wondible-com-wonlife.s3.amazonaws.com/WonLife-latest.zip)

[MacOSX Client](https://wondible-com-wonlife.s3.amazonaws.com/WonLifeMacOSX-latest.zip) - lightly tested

[Linux Client](https://wondible-com-wonlife.s3.amazonaws.com/WonLifeLinux-latest.zip) - lightly tested

Download and extract zip file. Copy the program and names files into the same folder as OneLife.exe (or equivalent).

> **Steam**: right click on `One Hour One Life`. Chose `Properties...` from the menu. One that dialog, choose `Local Files` on the left, and then the `Browse...` button. Copy the files into this directory.

## Example Configurations

The settings directory has three main subfolders. Copy the contents (ini files) of one folder into the game's settings directory.

- [Vanilla](#vanillaall-configuration---differences): Everything which can be disabled, is disabled
- [Plus](#plus-configuration): Enables most features, but does not drastically alter the interface
- [Wondible](#wondible-configuration): Main interaction mode is mouse **+ keyboard**. _**Do not use** without reading the description below._
- 2hol: Age Scaling configuration for Two Hours One Life
- defaults: How the program behaves with no setting files

| Feature                        |Vanilla|Plus|Wondible|defaults|
| -----------------------------: |-------|----|--------|--------|
| Bugfixes                       | ✔️     | ✔️  | ✔️      | ✔️      |
| Help Screen                    | ✔️     | ✔️  | ✔️      | ✔️      |
| R.I.P. name                    | ✔️     | ✔️  | ✔️      | ✔️      |
| Burn Rate                      | ✔️     | ✔️  | ✔️      | ✔️      |
| Time Hints                     | ✔️     | ✔️  | ✔️      | ✔️      |
| Say Quick Close                | ✔️     | ✔️  | ✔️      | ✔️      |
| Obj in Bad Biome               | ✔️     | ✔️  | ✔️      | ✔️      |
| Show Uses                      | ✔️     | ✔️  | ✔️      | ✔️      |
| Emotion Keys                   | ✔️     | ✔️  | ✔️      | ✔️      |
| Object Search                  | ✔️     | ✔️  | ✔️      | ✔️      |
| Craving Search                 |       | ✔️  | ✔️      | ✔️      |
| Person Search                  | ✔️     | ✔️  | ✔️      | ✔️      |
| Autorun                        |       | ✔️  | ✔️      | ✔️      |
| Follow roads only while running|       | ✔️  | ✔️      | ✔️      |
| Ignore Tall Objects            |       | ✔️  | ✔️      | ✔️      |
| Click Through Heads            |       | ✔️  |        | ✔️      |
| Open Say Field on Typing       |       | ✔️  | Upper  | Upper  |
| Tab Name Completion            |       | ✔️  | ✔️      | ✔️      |
| Tab Name Suggestion            |       | ✔️  | ✔️      | ✔️      |
| Drag Drop                      |       | ✔️  | ✔️      | ✔️      |
| Family Hearts                  |       | ✔️  | ✔️      | ✔️      |
| Mark Genetic Family            |       | ✔️  | ✔️      | ✔️      |
| Mark New Players               |       | ✔️  | ✔️      | ✔️      |
| Name Labels                    |       | ✔️  | ✔️      | ✔️      |
| Yum Hover                      |       | ✔️  | ✔️      | ✔️      |
| Time Based Hunger Dings        |       | ✔️  | ✔️      | ✔️      |
| Filter Matches Product         |       | ✔️  | ✔️      | ✔️      |
| Location Slips                 |       | ✔️  | ✔️      | ✔️      |
| Screen Push                    |       | ✔️  |        |        |
| Click to Move Lock to Interact |       |    | ✔️      |        |
| Keyboard Commands              |       |    | ✔️      | ✔️      |
| Camera Pan                     |       |    | ✔️      | ✔️      |

## Vanilla/All Configuration - differences

All features which can be disabled, are disabled. The following changes are not togglable and are always present.

### Bugfixes

Reset the sprite remap if you die while high. See [OneLife/#163](https://github.com/jasonrohrer/OneLife/issues/163)

### Help Screen

Changes the ESC overlay to include mod keys and help

### Out of Game

"WonLife" is on the main screen so you can tell the mod is running.

Shows "R.I.P. <name>" in place of "YOU DIED"

### Food Bar

Displays a line above the food bar, that shows approximate pip-per-minute drain.

### Hints

Shows hints with (time passing) for fires, dough, growing plants, etc so you can see when the thing you need to do is wait.

### Say Field

Press `F1` to close the say field without erasing it.
Press `shift-backspace` to close and clear the say field (e.g. "YOU ARE ... DEAD")

### Object Hover

Allows viewing object names when hovering in bad biomes

Shows the remaining uses of water buckets, bushes, piles, etc.

> Piles are defined by a category object id, defined in 
> `settings/categoryPile.ini`

### Additional UI

These features are present in all configurations, but can be ignored if you don't activate them.

#### Emotion Keys

Allows triggering emotes with Ctrl+key or Alt+key. Emote keys are defined in `settings/emotionKeys.ini` with these defaults. The emotion commands in the setting file are for convenience only, it uses line number like the base game settings. Note: Certain key combos may not work; Ctrl+q is interpreted as ESC for instance.

|Key| Command  |
|---| :------- |
| h | /happy   |
| m | /mad     |
| a | /angry   |
| s | /sad     |
| d | /devious |
| j | /joy     |
| b | /blush   |
| u | /hubba   |
| i | /ill     |
| y | /yoohoo  |
| f | /hmph    |
| l | /love    |
| o | /oreally |
| k | /shock   |

#### Object Search

Separate search filter with `:` puts an arrow on the nearest target object. If farther way it has a location slip, but only within the map buffer. The current search is shown in place of the craving.

#### Person Search

Search for a person's name with `:character name` (or a prefix), or by press `t` with the cursor over them to get a temporary location slip to them. If someone says "Follow me", you can.

> `settings/playerTrackKey.ini`

## Plus Configuration

Enables most features, but does not drastically alter the interface

### Autorun

Double-click to enable an auto-run mode. Dotted line trails will always be shown while active. Click again or catch your cursor to stop. You will only follow roads while running, so it less likely to get taken away unexpectedly.

> This feature can be adjusted or disabled by the setting file `settings/maxDoubleClickFrames.ini`. Set to 0 to disable double click to run; you can't click twice in 1 frame.
> `settings/followRoadsOnlyWhileRunning.ini`. Set to 0 to restore standard behavior.

### Hit Detection

Changes the hit detection of large objects (mainly trees) so they they only detect clicks on their tile, making it much easier to navigate through swamps and other dense areas. Main other affect I've noticed is that you cannot click on the cart part of a horse-cart.

> `settings/ignoreTallObjects.ini` (0 to disable this feature)

While in screen lock (spacebar), hit detection prefers the item in the tile to any characters who may be overlapping it, and provides the highlight effect seen most commonly seen with objects behind trees. Note that this can make it harder to eat, which makes me still slightly unsatisfied with this mode of activation.

> `settings/preferObjectsOverPlayersWithScreenLock.ini` (0 to disable this feature)

### Say Field

Automatically open the say field to talk if you type a text character. Does not block e/z; those character will be added if another printable character is seen shortly afterwards.

> `settings/openSayFieldOnTypingLower.ini` (0 to disable on lower case letters)
>
> `settings/openSayFieldOnTypingUpper.ini` (0 to disable on upper case letters)

`F2`-`F12` can be used as say field macros. (`F1` is taken by closing the say field) Ctrl+key with say open to assign text

> Values are saved when updated, or edit in `settings/textMacros.ini`
>
> `settings/textMacrosEnabled.ini`, 0 to disable this feature

#### Name Completion

Allows stepping through completions of player and grave names with tab key while say field is open.  Can recognize full names for "CURSE " or the beginning of first names otherwise.

#### Name Suggestion

Suggests random names or name completions by pressing tab with "I AM " or "YOU ARE " in the say field.

> This requires the name files from the game's source repository. They should also be packed in WonLife zip release. Place the files in the same folder as the game program.
> 
> - maleNames.txt
> - femaleNames.txt
> - lastNames.txt
> 
> `settings/tabNameCompletion.ini` (0 to disable these features)

#### Object Search

As above; If no object search is active, a search is performed for the current craving. This can be disabled with 

> `settings/defaultSearchForCraving.ini`, 0 to disable this feature

Open the the say field with `:` prefilled by pressing `;`.

> ` settings/searchOpenKey.ini` to change the key

Clear the current search by pressing `````

> ` settings/searchClearKey.ini` to change the key

### Drag-Drop

Allows holding the mouse button when picking up an item, once the character is shown as holding the item, the cursor will show the item, and it can be released on another tile to use the item there. Handy for water-to-crops, soil-to-crops, moving things, etc.

> `settings/dragDropUse.ini` (0 to disable this feature)

### Player Annotations

Shows heart above mother/grandmother, child/grandchild, siblings, twins. Currently includes aunts/uncles, still not sure about that part.

> `settings/showRelationDistance.ini` (0 to disable hearts)
> `settings/closeFamilySprite.ini`

Shows a gold ball above players who count for gene score, aka +FAMILY+ from the /FAM command.

> `settings/showGenticFamily.ini` (0 to disable gold disks)
> `settings/geneticFamilySprite.ini`

Shows a gosling on the head of new players (fuzzily defined as closely related births within one second of a 'YOUR BABY IS' message)

> `settings/showNewPlayers.ini` (0 to disable goslings)
> `settings/newPlayerMarkerObject.ini`

There are keybinds to increase (= aka unshifted +) or decrease (-) hearts for players of interest. Manual marking can go one size larger than mom/child.

> `settings/playerMarkKey.ini`
> `settings/playerUnmarkKey.ini`

Shows a name label to the side of characters of interest. Show for people you name yourself, and for those you hover for a second (e.g. looked at their name)

> `settings/showNameLabels.ini` - 0 to disable this feature

### Item Hover

Food item descriptions show Yum or Meh. Edible items and some precursor items are highlighted green (yum) or red (meh) on cursor over.

> `settings/showYumHover.ini` (0 to disable this feature)

### Food Bar

Starvation notices are based on time to starvation instead of food boxes, making them relative to clothing etc.

> `settings/starvationAlarmTime.ini` - number of seconds for starving state (twice that for hungry). Set to 0 to disable this feature.

### Hints

/filter selects all transitions that produce a matching object. So even if you can't spell tattoo, /tat gives you all the tattoo items with their immediate precursors (and potato recipes)

> `settings/filterMatchesProduct.ini` (0 to disable this feature)

### Location Slips

Reworks location markers. Replaces many instances of your character talking to itself with slips. Hover a slip to show distance when it would not normally be shown.

- Home slips are standard white. There can be up to 7 on screen, the most recent has the 'home' art.
- Map slips are blue, you can have more than one, standard lifetime
- Baby slips are your skin color
- Expert slips the target player's skin color
- Follower/Leader slips are badge color
- Bell slips are gold and apoc towers are red, you can have more than one
- Homeland slips are stone gray
- Slips to owned property. Property slips are wood brown
- Temporary slips have a pointer to the location when close.

> `settings/locationsSlipsEnabled.ini` (0 to disable this feature)

> Since monument colors require object specific information, they are settable in 
> 
> `settings/locationSlipColors.ini`
> 
> Format is
> `objectID r g b`

### Screen Push

Putting the pointer near the edge of the screen will nudge it over, as far as your character remains in frame.

> Push speed can be configured in `settings/screenEdgePushSpeed.ini`. Default value is 10, speed of 0 (or even 1) will disable edge push.

## Wondible Configuration

Most features as in Plus, main interaction mode is mouse **+ keyboard**.

**DANGER - if you don't understand what you are doing, you WILL NOT BE ABLE TO PLAY THE GAME.**

### DANGER: Click to Move Lock to Interact

> `settings/clickToMoveLockToInteract.ini` (0 to disable this feature)

Makes clicks by default move only. Lock the screen (spacebar) to perform all other functions. Alternately, you may use Ctrl or Alt to *not* lock the screen and perform actions; this works while the say field is open.

> `settings/preferObjectsOverPlayersWithScreenLock.ini` is off in the provided settings (keyboard commands cover this need).

### Keyboard Commands

Adds key actions that do very specific things at the mouse pointer cell, versus the default click which does very context sensitive things based on precise hit detection.

Press `F1` to close the say field without erasing it if you need to do something.
Press `shift-backspace` to close and clear the say field (e.g. "YOU ARE ... DEAD")

> This feature conflicts with openSayFieldOnTypingLower, which is disabled in this configuration.

> `settings/interactionKeysEnabled.ini` (0 to disable this feature)

Default bindings (change in `settings/interactionKeys.ini`)

|Key| Action                    |
|---| :------------------------ |
| q | step                      |
| a | autorun                   |
| f | use                       |
| d | drop                      |
| s | take/cycle from container |
| v | eat/self                  |
| g | feed/use on other         |
| k | kill                      |
| x | examine                   |
| r | put/take in backpack      |
| e | put in backpack           |
| w | take/cycle in backpack    |

Holding `c` will allow you to pan your view around within the map buffer.  With camera pan, it may look better if you change mouse pointer to `DRAWN`
Configuration disables screen edge push in deference to this feature.
