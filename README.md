## Wondible's One Hour One Life Client Patches

[Patched Windows Client](https://wondible-com-wonlife.s3.amazonaws.com/WonLife-latest.zip)

### custom-gitignore

Cleans up some noise from my local compile environment that apparently don't bother Jason. Perhaps he has global ignores for those files.

### show-modded-client

Prints "WonLife" on the start page so it's easy to tell when the mod has loaded, or the game has relaunced vanilla. This also adds same-program relaunch and client version mismatch testing.

Sets user agent to `client_wonlife`

### optional-client-tag

Attempts relogin with/without client tag if login fails.

Adds setting for which to try first, but updates setting on successful login.

`settings/usingClientTag.ini`

### screen-edge-push

Putting the pointer near the edge of the screen will nudge it over, as far as your character remains in frame.

Push speed can be configured in `settings/screenEdgePushSpeed.ini`. Default value is 10, speed of 0 (or even 1) will disable edge push.

### autorun

Double-click to enable an auto-run mode. Dotted line trails will always be shown while active. Click again or catch your cursor to stop.

This feature can be adjusted or disabled by the setting file `maxDoubleClickFrames.ini`. Set to 0 to disable double click to run; you can't click twice in 1 frame.

### click-through-trees

Changes the hit detection of large objects (mainly trees) so they they only detect clicks on their tile, making it much easier to navigate through swamps and other dense areas. Main other affect I've noticed is that you cannot click on the cart part of a horse-cart.

`settings/ignoreTallObjects.ini` (0 to disable this feature)

### diegetic-temperature

Characters shiver when cold, and get a sweat drop when hot. This applies to all characters, although the client does not receive temperature updates for other players who are standing still.

`settings/showShiverSweat.ini` (0 to disable this feature)
`settings/sweatDropSprite.ini`

### click-through-heads

While in screen lock (spacebar), hit detection prefers the item in the tile to any characters who may be overlapping it, and provides the highlight effect seen most commonly seen with objects behind trees. Note that this can make it harder to eat, which makes me still slightly unsatisfied with this mode of activation.

`settings/preferObjectsOverPlayersWithScreenLock.ini` (0 to disable this feature)

### open-say-field-on-typing

Automatically open the say field to talk if you type a text chracter. Does not block e/z; those character will be added if another printable character is seen shortly afterwards.

`settings/openSayFieldOnTypingLower.ini` (1 to enable on lower case letters)
`settings/openSayFieldOnTypingUpper.ini` (0 to disable on upper case letters)

### curse-assist

Allows stepping through completions of player and grave names with tab key while say field is open.  Can recognize full names for "CURSE " or the begging of first names otherwise.

`settings/tabNameCompletion.ini` (0 to disable this feature)

### name-assist

Suggests random names or name completions by pressing tab with "I AM " or "YOU ARE " in the say field.

This requires the name files from the game's source repository. They should also be packed in WonLife zip release.

- server/maleNames.txt
- server/femaleNames.txt
- server/lastNames.txt

Depends on curse-name-assist, uses same settings file

### fix-mushroom-death

Reset the sprite remap if you die while high. See [OneLife/#163](https://github.com/jasonrohrer/OneLife/issues/163)

### emotion-keys

Allows triggering emotes with Ctrl+key or Alt+key. Emote keys are defined in `settings/emotionKeys.ini` with these defaults. The emotion commands in the setting file are for convenience only, it uses line number like the base game settings. Note: Certain key combos may not work; Ctrl+q is interpreted as ESC for instance.

h /happy
m /mad
a /angry
s /sad
d /devious
j /joy
b /blush
u /hubba
i /ill
y /yoohoo
f /hmph
l /love
o /oreally
k /shock

### interacation-refactoring

Rewrite of some portions of pointer down and command issuing, depended on by other patches.

### drag-drop-use

Allows holding the mouse button when picking up an item, once the character is shown as holding the item, the cursor will show the item, and it can be released on another tile to use the item there. Handy for water-to-crops, soil-to-crops, moving things, etc.

### click-to-move-lock-to-interact

Disabled by default `settings/clickToMoveLockToInteract.ini` (1 to enable this feature)

Makes clicks by default move only. Lock the screen (spacebar) to perform all other functions. Alternately, you may use Ctrl or Alt to *not* lock the screen and perform actions; this works while the say field is open.

### interaction-keys

Adds key actions that do very specific things at the mouse pointer cell, versus the default click which does very context sensitive things based on precise hit detection.

Press F1 to close the say field without erasing it if you need to do something.
Press shift-backspace to close and clear the say field (e.g. "YOU ARE ... DEAD")

This feature may conflict with openSayFieldOnTypingLower.

`settings/interactionKeysEnabled.ini` (0 to disable this feature)

Default bindings (change in `settings/interactionKeys.ini`)
q step
a autorun
f use
d drop
s take/cycle from container
v eat/self
g feed/use on other
k kill
x examine
r put/take in backpack
e put in backpack
w take/cycle in backpack

### show-close-family

Shows heart above mother/grandmother, child/grandchild, siblings, twins. Currently includes aunts/uncles, still not sure about that part.

Shows a gold ball above players who count for gene score, aka +FAMILY+ from the /FAM command.

Shows a gosling on the head of new players (fuzzily defined as closely related births within one second of a 'YOUR BABY IS' message)

There are keybinds to increase (= aka ushifted +) or decrease (-) hearts for players of interest. Manual marking can go one size larger than mom/child.

`settings/showRelationDistance.ini` (0 to disable hearts)
`settings/closeFamilySprite.ini`
`settings/showGenticFamily.ini` (0 to disable gold disks)
`settings/geneticFamilySprite.ini`
`settings/showNewPlayers.ini` (0 to disable goslings)
`settings/newPlayeObject.ini`
`settings/playerMarkKey.ini`
`settings/playerUnmarkKey.ini`

### help-overlay

Changes the ESC overlay to include mod keys and help

### yum-hover

Food item descriptions show Yum or Meh. Edible items and some precuros items are highlighted green (yum) or red (meh) on cursor over.

`settings/showYumHover.ini` (0 to disable this feature)

### show-name-on-death-screen

Shows "R.I.P. <name>" in place of "YOU DIED"

### show-burn-rate

Displays a line above the food bar, that shows approximate pip-per-minute drain.

### show-learned-tools

Displays your learned tools and an empty slip for each available tool slot along the top of the screen. Similar to yum, the tool UI is only shown when holding or examining a tool. Available slots depends on the text announcements and may not be available after reconnects and such.

`settings/showLearnedTools.ini` (0 to disable this feature)

### filter-matches-product

/filter selects all transitions that produce a matching object. So even if you can't spell tattoo, /tat gives you all the tattoo items with their immediate precursors (and potato recipes)

`settings/filterMatchesProduct.ini` (0 to disable this feature)

### time-transition-hints

Shows hints with (time passing) for fires, dough, growing plants, etc so you can see when the thing you need to do is wait.

### tolerate-missing-graphic

Skips attempting to draw the hint arrow if the graphic is missing, which it may be in client folders for 2HOL etc. Game crashes otherwise.

### location-slips

Reworks location markers.

- Home slips are standard white. There can be up to 7 on screen, the most recent has the 'home' art.
- Map slips are blue, you can have more than one, standard lifetime
- Baby slips are your skin color
- Expert slips the target player's skin color
- Follower/Leader slips are badge color
- Bell slips are gold and apoc towers are red, you can have more than one
- Homeland slips are stone gray

`settings/locationsSlipsEnabled.ini` (0 to disable this feature)

Since monument colors require object specific information, they are settable in 

`settings/locationSlipColors.ini`

Format is
`objectID r g b`

### age-scaling

Clientside age scaling for e.g. Two Hours One Life, where you currently spend half your life old and wrinkled. Allows settings multipel scaling segments, an example file is provided for 2HOL

`settings/ageScaling.ini` - Client uses this files, shows do-nothing settings for vanilla.
`settings/ageScaling2hol.ini` - 2HOL example settings - copy to `ageScaling.ini` to use

File format:
`serverAge displayAge optional comment, rest of line ignored`

e.g.

`3 3` - if the server reports 3, show as 3

`120 60` - if the server reports 120, show as 60

## show-bad-biome-objects

Allows viewing object names when hovering in bad biomes

## show-use-count

Shows the remaining uses of water buckets, bushes, piles, etc.

Piles are defined by a category object id, defined in 

`settings/categoryPile.ini`

## object-search

Search filter (/) also puts an arrow on the nearest target object. If farther way it has a location slip, but only within the map buffer.

### Patch Development

I had a [fork](https://github.com/JustinLove/OneLife) of the [git repo](https://github.com/jasonrohrer/OneLife), but felt like the several features could get a bit muddled all in one, and buried behind mainline changes and merges.

I'm currently using [Stacked Git](http://procode.org/stgit/) (stgit) to manage patches, although it seems to create a lot of noise in the commit graph.

Importing all of these patches would be:

`stg import --series onelife-client-patches/series`

