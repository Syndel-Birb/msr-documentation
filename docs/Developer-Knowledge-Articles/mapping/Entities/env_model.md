# env_model

The best way to load fairly static .mdl files that do not need a script.

## Properties

* model modelname
    - Model with path (msc is treated as the root).
* body submodelindex
    - Submodel to display * currently seems bugged
* sequency integer
    - Animation sequence to play
* framerate float
    - Animation speed to use (1 = normal frame rate, 0.5 = half frame rate, 1.5= 150% frame rate)
* rendercolor RRR BBB GGG
* renderfx [1-16]
* rendermode [1-5]
    - Rendering properties, see: Half-Life Rendering Properties
* dmg 0|1
    - When set to 0, model is non-solid.
* mins
* max
    - Not entirely sure how these two work, but they have something to do with the model's bounding box, I think. I'd leave them at their defaults.
* angles PITCH YAW ROLL
    - As per usual, the direction the model will face
* targetname targetname
    - You can use this targetname to affect this model with other entities,

## Example

```cpp title="Image of Calrian model." linenums="1"
{
"targetname" "calghost"
"angles" "0 90 0"
"maxs" "16 16 36"
"mins" "-16 -16 0"
"rendercolor" "0 0 0"
"renderamt" "1"
"rendermode" "5"
"renderfx" "16"
"framerate" "1"
"model" "models/monsters/skeleton2.mdl"
"classname" "env_model"
}
```