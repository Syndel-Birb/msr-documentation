# msitem_spawn

## Properties

* scriptfile "scriptfile"
    - Look at the scripts Repository structure to get filepath.
* duration "seconds" (time before item vanishes - but the longest it will stay is about 30 secs, regardless of setting.)
* spawnstart "0|1" (when set to 1 entity must be triggered before item appears, recommended)
* targetname "targetString" (each time this is triggered, item appears)
* (angles, origin)

## Example

```cpp title="Medium Health Potion" linenums="1"
 {
"origin" "2071 911 1432"
"scriptfile" "health_mpotion"
"duration" "9999"
"targetname" "freepot"
"spawnstart" "1"
"classname" "msitem_spawn"
}
```