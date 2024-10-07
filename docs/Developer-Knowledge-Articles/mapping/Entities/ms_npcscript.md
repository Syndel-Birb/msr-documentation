# ms_npcscript

ms_npcscript can be used to make an individual NPC or monster move to a specific locale, or play a particular animation. Some NPC's and monsters have special 'eventnames' that make them do special things.

## Properties

* Target - The monster or npc to be affected (matches targetname of the npc you intend to affect)
* Type - The type of NPC script
    - 0 = make this the movement destination for the npc
    - 1 = play an animation (use Jed's Model Viewer to determine which animations sequence names are available.)
    - 2 = Run script event, ie. use one of the NPC's embedded eventname's (see more below)
    - 3 = Move, then play anim - move to this location, then play the animation
    - 4 = Move, then Run Script Event - move to this location, then use the eventname.
* Moveanim - which animation to use while moving (most NPC's have walk and run animations)
* Actionanim - which animation to play for Type1 or Type3.
* Eventname - the eventname to use for Type2 or Type4 (see below)
* firewhendone - After the movement is made and/or animation is played, trigger this map event
* firedelay - Delay before event starts
* stopai - Setting to 1 disables the monster AI (prevents monster from attacking, etc.)

Eventnames: There are far too many available eventnames to list them all here - but here's some examples:
calruin/cavetroll (Lord BS) - responds to: give_clubs (give him his clubs), invincible_on, vulnerable (toggles invulnerability)
monsters/orc_unarmed (developer orc) - responds to: superorc (godmode), godoff (returns to vulnerable)
The orc warboss - godon_warboss, offgod_warboss, infernal_warboss (adds fire damage), normal_warboss (returns to normal)
Atholo and Undamael - vulnerable (makes vulnerable - both are invulnerable by default)
All specific keyholes - return_keys (causes keyhole to return any keys used after this event is run)

Universal Eventnames:
for use with ms_npcscript, these work with most NPCs, including monsters/lure:
XXXX_race - where XXXX is, replace with desired race. This is buggy, and may cause issues (including crash). Common uses include: orc_race, hated_race, beloved_race, human_race. Full faction list and relations can be found here.
ELEMENT_immune: Where ELEMENT is, replace with desired element. Valid elements currently include: lightning, fire, poison, and cold. Using normal_immune sets all immunities to normal (including any immunities the creature might normally have).
fifty_armor - sets 50% damage absorption.
eighty_armor - sets 80% damage absorption.
make_invulnerable - makes monster invulnerable (godmode)
make_vulnerable - makes monster vulnerable
add_XXX_health - where XXX is use 10, 100, 500, or 1000 (untested)
double_health - Doubles creature's health based on current. Prefixes name with "Strong ", can be used repeatedly (but name effect stacks)
quad_health - Quadruplescreature's health based on current. Prefixes name with "Very Strong ", can be used repeatedly (but name effect stacks)

Note that: sometimes second spawns of monsters will not respond to the eventname requests from the ms_npcscript, if they were used on the first spawn. This does not seem to affect playanim nor movement requests, however.

If you have issues with a monster being 'stuck' after running a script event such as quad_health on him, add an animation the monster has to actionanim and moveanim. If yer not sure, "idle" is usually a safe bet.


## Example

```cpp title="Causes Edrin to freak out when you step on his flowers in Edana." linenums="1"
 {
"angles" "0 260 0"
"targetname" "edrinstrict1"
"firewhendone" "edrinspot"
"eventname" "trig_flowercompliant"
"moveanim" "run"
"target" "edrin"
"firedelay" "4"
"type" "4"
"classname" "ms_npcscript"
}
```