# Changelog - feature changes

## 83

- block many instances of your character talking to itself
- location slips temporarily give close distances
- location slips show distance when hovered
- slip to owned property
- /FAM gives location slips instead of speech
- follow roads only while autorunning
- fix bug with object search in containers

## v82

- C considers 0 a valid `char*`

## v81

- Rewrite readme as user focused, move old readme to READEM.patches.md
- Changed defaults for camera control to screen pan instead of edge push

## v80

- moved settings into several different example configuration subdirectories, copy the settings from the one you want to start with.

## v79

- fix-ghost-sounds was merged upstream
- showShiverSweat defaults to off

## v78

- fix tool slots for more learned tools than slots. Showing tools is disabled by default (if you have a setting file, you may still need to change it)
- new patch to fix some missing strings in 2hol

## v76

- drag drop has a setting file
- player search can find known graves
- ranged use key actions from outside of range will not move towards the target (e.g. the wolf)
- backpack use key will work on special clothing, e.g. take a bow from backpack or quiver
- twin's name is known
- show time hints for objects that disappear

## v75

- Camera control should no longer be windows-only
- patch for ghost horses and other sounds

## v71

- New setting to disable default search for craving

## v70

- mother's name is know
- search for craving food when no object search active
- reduce pathing distance in some cases with key command (e.g. picking carrots to a box travels to adjacent tile instead of carrot tile)
- fix running on roads
- attempt to fix end of life music with age scaling

## v69

- login mode is only recorded on the first success. The main server accepts both formats, and it's possible for a transient error to flip us into old mode and get stuck there. You may want to check settings/usingClientTag.ini is 1 for the main onelife servers.
- prevent sending use slot parameter on older servers
- The current object search is shown in place of craving, including a message if no matching object names were found.
- Player slips show the first few letters of the name so they can be distinguished.

## v68

- screen edge push combined with new camera movement as camera-control
- hold 'c' to move the screen view around with the loaded area of the map

## v67

- patch to block new client messages, e.g. for 2hol
- player search and object search use : instead of /

## v65

- hunger dings are based on time to starvation instead of food boxes, making them relative to your clothing etc.
- fix yum hover for yumID

## v63

- name labels for characters you name or hover for a moment.

## v62

- Temporary location slips have a pointer to the spot when close
- Person search: /character name, or press the key ('t' by default) when the cursor is over them gives a temporary location slip to the person. When someone says "follow me", you can.

## v57

- Object fitler (/) will search for that object. It has an arrow, and a location slip when farther away (but still only in the map buffer area)
- new settings: sweatDropSprite, closeFamilySprite, geneticFamilySprite, and newPlayerMarkerObject

## v55

- Expert location slips are target player's skin color
- Homelands are grey bell slips. May revise visibility.
- Old slips will fade and yellow a bit
- fix memory leak in object search

## v54

- Seems level 2 apoc tower was missing from slip colors
- No change, but walk to front of shelves is now vanilla.

## v53

- Location slips can be disabled with a setting file
- Baby location slips are your skin color
- Add "USES" to the uses item description

## v50

- New players have a gosling on their head.
- Shows the use count of water buckets, bushes, piles, etc.
- Use server-provided tool slot info instead of message parsing

## v49

- Fix awkward pathing bug
- Bonus feature: path to front of wall shelves when approaching from behind.
- Allow viewing names of objects in bad biomes
- Replaces custom help screen with changes to ESC screen

## v48

- Location slips are back. Babies are pink, and follower/leader are badge color.
- There is now a gold disk above players who score aka +FAMILY+
- Family hearts above hat.

## v45

- correct 2hol infertile age
- remove hotfix for running patch
- location-slips is disabled until it can be updated for baby/leader/follower

## v44

- age scaling patch, e.g. for nicer display on 2HOL
- hotfix for characters jumping around while running
- fix family hearts for sideways babies

## v43

- location slips bells are on the side, trying multiple home markers with most recent using the 'home' art.

## v42

- reworked location slips with multiple bells and maps
- changed *default* help overlay key to '\' (I keep hitting 'h' by accident)

## v40

- tolerate missing hint arrow graphic on mod folders (e.g. 2HOL)

## v39

- Tool UI centered, improved physicality, blocks learned messages, settings file.
- Screen edge push can push farther (while not moving).
- time transition hints returns; vanilla version didn't really do it.
- /filter selects all transitions that produce a matching item.

## v38

- WIP tool UI

## v37

- show pip-per-minute burn rate as line above food bar
- test removing patch to auto move ends. It was causing flip-flop on short moves.

## v34

- using agent `client_wonlife`
- Supports logging into agent and agentless servers

## v33

- patch conflict resolution

## v32

- Old STG can't import formatted patches
- Fix last name suggestions

## v31

- Remove time-transition-hints, as this is supported in vanilla
- Consider diagonal length when pathing near an action target
- Bugfix for dropping in cell with not orthagonal access

## v30

- Uses male/female names for name completion of held babies. Name files in zips have been updated.
- Remove inline doublePair syntax patches

## v29

- show name on death screen
- send additional parameter with USE commands
- auto run prefers to travel on roads, instead of ignoring them as it used to

## v28

- fix merge conflicts

## v27

- yum hover now highlights many precursor items (gooseberry bush, burdock plant, stew pot, etc)
- handle swapping held horse with item
- put-in-backpack key does not remove item if hand empty
- take-from-backpack key does not remove backpack if empty

## v26

- fix merge conflicts.
- continuous run patch removed (merged)
- Does not yet incorporate revised ground swapping, other interaction changes need review.

## v25

- fix merge conflicts

## v24

- Shows hearts above close family
- Keybinds to manually adjust player heart sizes
- Shift+backspace will clear and close the say field (e.g. "YOU ARE ... DEAD")
- "Play at your own risk" button on version mismatch message
- Patch for single frame character facing flips while running

## v23

- Kill key now uses nearest player search, like main game. This is currently applied to all player action keys (pickup/use-on)

## v22

- fix merge conflict

## v21

- Kill key should work like shift-rightclick.
- F1 will close the say field without erasing it.
- Ctrl or Alt also allows interaction with clickToMoveLockToInteract. These can be used while the say field is open.
- Emote keys can now be used with Ctrl modifier in addition to Alt.
- New feature: highlight foods as Yum or Meh

## v20

- Remove position patches (merged to main codebase) and fix conflicts

## v19

- Open say field on typing split into upper and lower case settings files. By default only upper is enabled
- New, disabled by default: click by default moves, lock screen to interact
- Keyboard commands that do specific things at mouse pointer cell.
- Help overlay, press 'h' by default

## v18

- Allows triggering emotes with modifier keys combination. 
- drag-drop-use: Hold the mouse button when picking up an item, release to use.
- List of files to include in build packages is now stored in this repository.

## v17

- Fix certain characters for auto open say (notably capital I, N, M)

## v16

- patches add settings files to source directory
- open say field on typing now has a setting file
- tab name completion now has a setting file

## v15

- Remove container patch

## v14

- Temp patch for container click change which blocked picking up basket on tule stumps, horse carts, and, I hear, fishing poles.

## v13

- Auto-open say field is disabled in VOG mode.
- Reset sprite remap if you die while high

## v12

- Includes patches for client position discrepancies, usually visible as draw inversion or can't pick up baby.

## v10

- Should relaunch mod from game updates and fps detect.
- Attempts to detect changes in base game client version and notify player, with a download link.

## v9

- Prints "WonLife" on login screen
- Automatically opens say field if printable characters are typed
- Player name completion, in particular with "CURSE "
- Name suggestion for "I AM " and "YOU ARE "

## v8

- Adds time based transitions to crafting hints.

## v7

- All features can now be disabled by settings files
- Autorun allows interacting with the object clicked to end the run.

## v5

- Click through heads with space held
