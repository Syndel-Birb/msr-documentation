# msarea_monsterspawn

This entity can be a pointentity, OR brushentity for compatibility. Using the pointentity version of this is most recommended.

## Properties

* targetname spawnAreaName
    - monsters with spawnarea property matching this are tied to this monsterspawn area
* spawnloc "0|1"
    - [optional] 0 = Monster's spawn at their own origin, 1 = Monsters spawn within the bounding box of the brush (careful with the latter, it may cause monsters to be stuck in walls or one another). Note also when setting this to 1 that spawn areas are always box shaped, and thus msarea_monsterspawn's must always be made of a single, boxed brush - they cannot be assembled from multiple solids nor solids of anything but a basic box or rectangular shape.
* "spawnstart" "1"
    - [optional] If set, monsters tied to this will not spawn until this entity is triggered (target'ed) by another. This is usually recommended, as it prevents errors and CPU load issues.
* "fireallperish" "triggerName"
    - [optional] Triggers entity with targetname matching triggerName, when all monsters tied spawn are slain [out of respawns]. This has some bugs that sometimes prevent it from working proper (see below).
* (angles, origin)

### Usage as a Brushentity Warning

Brush monster spawns were always iffy, but even more so in MS:C, so don't use brush area spawns and spawnloc 1 unless you have no other choice - and then be very careful there is PLENTY of space between the monsterspawn brush and anything you don't want your monsters inside of (walls, trees, etc) leave 128+ units. Do not 'break up' monster spawn brushes by linking multiple spawns into a single entity. Each spawn should be but one single brush.

## Example

```cpp title="Example:" linenums="1"
{
"fireallperish" "finalwave_dead"
"spawnstart" "1"
"targetname" "finalwave"
"classname" "msarea_monsterspawn"
}
```

## Usage Tips

You always want to use an msarea_monsterspawn together with any of the msmonster_xxx or ms_npc entities. Otherwise you cannot control how many lives the creatures have, when they spawn, or their grouping. In addition you can generate CPU lag or MOD:Extra_Data Precache errors. You can, of course, tie multiple monsters or NPC to the same msarea_monsterspawn by defining each monster's spawnarea property accordingly.

It is common practice to have an msarea_monsterspawn named "global", for all wandering monsters of non-consequence throughout the map. However, too many active monsters will lag a server, so it's best to have most monsters only spawn when players enter a certain area, or trigger a certain event. Common entities used for doing this include trigger_once and func_breakable.

### Using Monster Deaths as Triggers

* Fireallperish "targetname"
    - As mentioned, this property of msarea_monsterspwan is fired when all the monsters tied to it are out of respawns. There is a recurring bug with this. If you have monsters of different types with different numbers of lives, there's a chance that the event will not fire. So keep that in mind when building monsterspawns.

    - MS:C Note: Actually, it got worse with MS:C. You can activate single events with Fireallperish - but chaining monster spawns together is haphazard. For a workaround, see alternate trigger_counter method described in yonder thread.

    - Common uses the Fireallperish target to trigger doors, break open walls leading to new areas via func_breakable, multi_managers to do multiple tasks with special effects, or spawn yet more monsters, by triggering another monster spawn.

* Killtarget
    - The killtarget property of msmonster_xxx or ms_npc, instead of removing an entity, triggers it. As such you can use this to trigger an event when an individual monster dies.