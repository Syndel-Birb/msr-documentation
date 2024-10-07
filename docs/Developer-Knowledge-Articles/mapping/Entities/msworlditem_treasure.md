# msworlditem_treasure

The entity used to represent a chest scriptfile in a map.

## Properties

* scriptfile scriptfile
    - Look at the scripts Repository structure to get filepath.
* defscriptfile "worlditems/treasurechest"
    - [optional] (seems to be primarily for compatability)
* delayhigh seconds (maximum delay before treasure appears)
* delaylow seconds (minimum delay before treasure appears)
* spawnchance [1-100] (chance of treasure appearing)
* spawnarea spawnAreaName
    - [optional] You can tie this to a msmonster spawn with "spawnstart" set to 1, so the chest will only appear when said spawn is triggered.
* targetname targetString [optional] (Used by other entities to affect this item)
* (angles, origin)

!!! note
    Delayhigh, delaylow, and spawnchance often have no effect, but should be kept for compatibility reasons.

!!! warning
    Players can access treasure chests through walls, if they are thin enough. Do not spawn treasure chests until the players are supposed to be able to get them.

## Example
```cpp title="Edana Mayor's Treasure Chest" linenums="1"
 {
"spawnchance" "100"
"targetname" "mayorstreasure"
"scriptfile" "edana/eTC1"
"defscriptfile" "worlditems/treasurechest"
"delayhigh" "300"
"delaylow" "30"
"classname" "msworlditem_treasure"
}
```