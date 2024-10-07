# mstrig_relay

## Properties

* target triggerName (map event to fire)
* triggerstate "0|1|2" [optional] (see trigger_relay's triggerstate description)
* random "integer" (percent chance of the target to be triggered)
* targetname "triggerName" (this entity must be triggered, common methods would be trigger_once, or trigger_multiple)
* spawnflags "1" [optional] (as there is no official documentation, I've no idea what this spawnflag does, but I if it works like trigger_relay, then setting this one will cause the entity to 'remove on fire' - meaning it can only be triggered once, but cleans itself up afterwards for better map optimization.)



## Example

```cpp title="10% chance for 'orcraid' to fire, when this entity itelf is triggered." linenums="1"
{
"origin" "-1600 -64 96"
"target" "orcraid"
"random" "10"
"triggerstate" "2"
"targetname" "rand_orcraid"
"spawnflags" "1"
"classname" "mstrig_relay"
}
```