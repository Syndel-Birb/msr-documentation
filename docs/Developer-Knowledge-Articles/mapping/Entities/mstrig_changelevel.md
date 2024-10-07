# mstrig_changelevel

If this entity is triggered, it will foce the players to the indicated map.

## Properties

* desttrans "messageString " (message of ms_player_spawn on dest map, see msarea_transition description)
* destmap "bspname" (sans the .bsp)
* targetname "triggerName" - this event must be triggered



## Example

```cpp title="Trigger changing back to a specific Thornlands map transition." linenums="1"
 {
"desttrans" "NE-A3"
"destmap" "thornlands"
"targetname" "backtothornlands"
"classname" "mstrig_changelevel"
}
```