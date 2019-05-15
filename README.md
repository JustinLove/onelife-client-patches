## Wondible's One Hour One Life Client Patches

[Patched Windows Client](https://wondible-com-wonlife.s3.amazonaws.com/WonLife-latest.zip)

### custom-gitignore

Cleans up some noise from my local compile environment that apparently don't bother Jason. Perhaps he has global ignores for those files.

### fix-auto-clicks-at-end-of-path

Fix for automatic clicks happening just before stopping movement.

The code for continuous running (mouse hold) runs just before the
end-of-move detection, so it possible to have an automatic move occur as
the character reaches their current destination, resulting in the
character stopped with an outstanding path (which had been sent to server)
and destination position different than current position.

Updating the move end position prevents the later code from immediately
ending movement.

### path-over-truncation

Fix up over-truncation in player update.

I believe this fixes draw inversion, and perhaps unable to pickup baby, due
to player position discrepancy on the client. It was possible for truncation
of paths during PLAYER_UPDATE to leave a single step path after truncation,
which the code elsewhere takes steps to prevent. The path execution code
will use the next path location without checking length, causing it to path
beyond the current destination position.

This patch extracts a function from the code which fixes up over-truncated
paths during PLAYER_MOVE in order to use it during PLAYER_UPDATE.

### additional-path-clears

Additional player path clears.

These are less certain to be issues, but I discovered possible path and
destination discrepancies while investigating position issues. This add some
additional path resets where current and destination positions were forced.

### show-modded-client

Prints "WonLife" on the start page so it's easy to tell when the mod has loaded, or the game has relaunced vanilla. This also adds same-program relaunch and client version mismatch testing.

### screen-edge-push

Putting the pointer near the edge of the screen will nudge it over, up the normal limits used by the game engine.

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

### click-through-heads

While in screen lock (spacebar), hit detection prefers the item in the tile to any characters who may be overlapping it, and provides the highlight effect seen most commonly seen with objects behind trees. Note that this can make it harder to eat, which makes me still slightly unsatisfied with this mode of activation.

`settings/preferObjectsOverPlayersWithScreenLock.ini` (0 to disable this feature)

### time-transition-hints

Adds TIME + A = B hints for objects with automatic changes, such as fire to coals, dough to leavened dough, etc.

This didnt do as much for finding relevant precursors as I hoped, such as

- Making Milkweed (Milkweed Seed Not Relevant)
- Making Milkweed Seed (Fruiting Milkweed Not Relevant) - this shouldn't even be time based?

More work is needed.

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

- server/firstNames.txt
- server/lastNames.txt

Depends on curse-name-assist, uses same settings file

### fix-mushroom-death

Reset the sprite remap if you die while high. See [OneLife/#163](https://github.com/jasonrohrer/OneLife/issues/163)

### emotion-keys

Allows triggering emotes with modifier keys combination. Alt+key works for me, Ctrl+key is reported to work for others. Emote keys are defined in `settings/emotionKeys.ini` with these defaults. The emotion commands in the setting file are for convenience only, it uses line number like the base game settings.

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

Makes clicks by default move only. Lock the screen (spacebar) to perform all other functions.

### interaction-keys

Adds key actions that do very specific things at the mouse pointer cell, versus the default click which does very context sensitive things based on precise hit detection.

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

### help-overlay

Shows a help overlay for interaction keys and emote keys. Default keybind is 'h', change in `settings/showHelpOverlayKey.ini`

### Patch Development

I had a [fork](https://github.com/JustinLove/OneLife) of the [git repo](https://github.com/jasonrohrer/OneLife), but felt like the several features could get a bit muddled all in one, and buried behind mainline changes and merges.

I'm currently using [Stacked Git](http://procode.org/stgit/) (stgit) to manage patches, although it seems to create a lot of noise in the commit graph.

Importing all of these patches would be:

`stg import --series onelife-client-patches/series`

