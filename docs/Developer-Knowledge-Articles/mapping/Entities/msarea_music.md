# msarea_music

## Identical Entities

mstrig_music

## Properties

* Custom Key/Value:
    - "musicname.mp3" "minutes:seconds"

## Example

```cpp title="msarea_music that plays the Thornlands music." linenums="1"
 {
"msthornlands_exterior.mp3" "3:00"
"classname" "msarea_music"
}
```

## Usage Tips and Limitations

By default, the mp3 to be played is assumed to be in the msc/music folder-but you can build paths to other folders. Currently only the minutes property is used, so be sure to place at least 1 more minute than your song actually is intended to loop. The new music will only begin to play on players who have touched the entity.

* MP3 cannot contain any ID1/2/3 tags
* MP3 must have a bitrate of 256Kps or less
* MP3 must be sampled at 48000 or 44000 hz
* Must be CBR (no VBR files)
* No spaces or non ASCII chars in the MP3's filename