# game-jam

pinball game

basic todos
- fix coordinate system box2d <-> sprite gfx.
- add prj to git
- design field


Dot matrix display
http://www.1001fonts.com/high-speed-font.html?text=EXTRA%20BALL%20IS%20LIT&size=60&fg=b10202&bg=000000

ideas
-------
revive
extra ball
objectives
headshot
medals
dogtags
jackpot
bonus multiplier


PlayingState
boolean gameInProgress;

	int ballNumber;
	int extraBalls;
	int totalBalls = 3;

	long score;
	int scoreMultiplier;
	int bonusScore;
	int bonusMultiplier;
	boolean multiplierHeld;

Abstract FieldElement
-ElementID
- Score for hitting element

BumperElement
applies an impulse to a ball when hit. should give score, shoud play sound 

DropTargetGroup
represents a set of drop targets, which are segments that disappear when hit. When all targets are
hit, the Field delegate is notified, and if the reset parameter is set, the targets will reappear after a delay.

Flipper Bat

RolloverGroup
represents a collection of rollover elements, such as the rollovers in the top lanes. They are activated (and
optionally deactivated) when a ball passes over them. Individual rollovers in the group are represented by instances of the
Rollover nested class, which specify center, radius, and color. Parameters at the collection level control whether the
rollovers should cycle when flippers are activated, and whether rollovers can toggle from on to off.

Sensor
used to identify areas on the table that should cause custom behavior when the ball enters.
SensorElements have no bodies and don't draw anything. The area they monitor can be a rectangle defined by the "rect" parameter as a [xmin,ymin,xmax,ymax] list, a circle defined by the "center" and "radius" parameters. During every tick() invocation, a sensor determines if any of the field's balls are within its area, and if so calls the field delegate's ballInSensorRange

Wall Arc

Wall

Wall Path
which represents a series of wall segments. The segments are defined in the "positions" parameter as a
 list of [x,y] values, for example: { "positions": [[5,5], [5,10], [8,10], [5, 15]] }
