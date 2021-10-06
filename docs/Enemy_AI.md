# AI #

## Enemy Shooter ##

Do nothing if no player units are within detection distance.

If a player unit is inside detection distance, lock attention to that unit, even if other units enters detection distance. When attention is locked to a unit and it is within shooting distance/area, shoot at player unit. Follow unit if it moves out of shooting distance/area and is not dead and still within detection distance.

```pseudocode

While nothing is detected:
	idle

"unit" moves into collision box "detection":
	if("target" != null):
		"target" = "unit"  # lock enemys attention to target

	while("target" != null and "target" inside detection):
		AttackTarget("target")
	
	"target" = null

AttackTarget("target"):
	if("target" is in "shootRange"):
		shoot at "target"
	else if(target is not destroyed):
		move towards target for at least [2 sek]
	else:  # Target is dead
		"target" = null

```