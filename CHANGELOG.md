# Changelog - feature changes

## v45

- correct 2hol infertile age
- remove hotfix for running patch

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
