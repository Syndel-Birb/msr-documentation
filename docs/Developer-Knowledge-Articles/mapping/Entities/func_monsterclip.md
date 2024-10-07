# func_monsterclip

## Properties

* targetname targetname - You can use the targetname to remove this clip later, but it is strongly suggest you do not use this to pen monsters in until players come near - instead simply do not spawn the monsters until players are present.

!!! warning
    Use func_monsterclip to create an invisible wall that only monsters obey. Beware, monsterclips are not perfect - sometimes monsters will slip through - they are particularly iffy if they border another brush entity (such as water, or a func_breakable). So try to surround them with solids and don't try to make fancy staircases with them as you might do with a clip textured brush. Also be VERY careful not to place your monsterclips in such a way that players can simply hide behind them and kill monsters at will.