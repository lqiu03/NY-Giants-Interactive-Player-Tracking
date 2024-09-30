# NY-Giants-Interactive-Player-Tracking
10 frames per seconds player tracking for NY Giants 2021-22 offensive play-calling 

**(X, Y) Coordinate Definition:**
![截屏2024-09-30 上午12 45 26](https://github.com/user-attachments/assets/f2535a6a-1e27-4229-a582-cc217fd43410)

**Files giants_all_players_movement.zip contains player tracking data from 2021-22 NFL Season NY Giants Week 1-8.**

**Dataframe definition:**
gameId: Game identifier, unique (numeric)
playId: Play identifier, not unique across games (numeric)
nflId: Player identification number, unique across players. When value is NA, row corresponds to ball. (numeric)
frameId: Frame identifier for each play, starting at 1 (numeric)
time: Time stamp of play (time, yyyy-mm-dd, hh:mm:ss)
jerseyNumber: Jersey number of player (numeric)
club: Team abbrevation of corresponding player (text)
playDirection: Direction that the offense is moving (left or right)
x: Player position along the long axis of the field, 0 - 120 yards. See Figure 1 below. (numeric)
y: Player position along the short axis of the field, 0 - 53.3 yards. See Figure 1 below. (numeric)
s: Speed in yards/second (numeric)
a: Acceleration in yards/second^2 (numeric)
dis: Distance traveled from prior time point, in yards (numeric)
o: Player orientation (deg), 0 - 360 degrees (numeric)
dir: Angle of player motion (deg), 0 - 360 degrees (numeric)
event: Tagged play details, including moment of ball snap, pass release, pass catch, tackle, etc (text)

**PFF Scouting data**

**Data frame definition:**
gameId: Game identifier, unique (numeric)
playId: Play identifier, not unique across games (numeric)
nflId: Player identification number, unique across players (numeric)
pff_role: The player's role on this play (text)
Possible values:
Coverage: Defensive player. Player whose initial goal is to play man or zone coverage
Pass: Offensive player. Player identified as the passer
Pass block: Offensive player. Anyone fully blocking a defender from the QB, or anyone in a clear pass block stance
Pass route: Offensive player. Any player not identified as a Pass Blocker or Passer
Pass rush: Defensive player. Any player whose initial intent is to rush the passer
pff_positionLinedUp: Position that the player was aligned at the snap of the ball on this play (text)
pff_hit: If player is a defensive player, indicator for whether they are credited with recording a hit on this play (binary)
pff_hurry: If player is a defensive player, indicator for whether they are credited with recording a hurry on this play (binary)
pff_sack: If player is a defensive player, indicator for whether they are credited with recording a sack on this play (binary)
pff_beatenByDefender: If player is a blocking offensive player, indicator for whether they are by a defender but was not charged for yielding a hit, hurry or sack (binary)
pff_hitAllowed: If player is a blocking offensive player, indicator for whether they are responsible for a hit on the QB (binary)
pff_hurryAllowed: If player is a blocking offensive player, indicator for whether they are responsible for a hurry on the QB (binary)
pff_sackAllowed: If player is a blocking offensive player, indicator for whether they are responsible for a sack on the QB (binary)
pff_nflIdBlockedPlayer: If player is a blocking offensive player, the nflId of the first defender the offensive player blocked (numeric)
pff_blockType: If player is a blocking offensive player, the type of block that the offensive player is executing on the defender (text)
Possible values:
BH: Backfield Help - A block from a player aligned in the backfield on which the blocker merely helps on a block rather than fully engaging his assignment. Usually seen when a blocker is clearing up a block or picking up a defender when he has broken through or been missed by another blocker
CH: Chip Block - This is only to be used for players who chip a pass rusher when they release for their route
CL: Second Level – A block made at the second level, this must be at least two yards across the line of scrimmage
NB: No Block - If a blocker executes no block on a play but simply runs his path or takes his pass set then we will note him with one all blocking line with this block type
PA: Play Action Pass Protection - A blocker pass protecting inline on a play action pass selling the play action by stepping in to show a run block before converting to pass protect
PP: Pass Protection - A standard pass protection block from an inline blocker
PR: Pocket Roll Block - This block type will be used any time the offense is executing a “rolling pocket” by which the entire offensive line moves with the QB’s rollout to stay in front of him but without ever taking a “conventional” pass set. There will be flexibility here to record the PR – Pocket Roll Block type in the same way as PA & RP block types in that individual matchups & responsibilities won’t always be obvious or necessary, so PR block types can be recorded by multiple blockers on an individual defender on the same play
PT: Post Block - A post block by an offensive player in pass protection to control a defender for another blocker while clearly demonstrating that he is not, at least initially, trying to fully engage with the block
PU: Backfield Pickup - A pass protection pick-up by a player aligned in the backfield
SR: Set & Release - A blocker who sets to pass protect a defender before releasing. This block will cover both players releasing from a set to block for a screen as well as “hold ups” by tight ends before they leak into the flat
SW: Switch Block - A blocker who passes off (or attempts to pass off) a defender. Most often used on stunts but can also be used for pass offs when pass rushers are slanting across the pocket or interior defenders are working to the edge to replace a dropping edge rusher, with an interior offensive lineman passing them out rather than staying with them
UP: Pull Pass Protection - A blocker pulling in pass protection from an inline alignment to block a defender in pass protection
pff_backFieldBlock:If player is a blocking offensive player, indicator for whether block occured in offensive backfield.

**Player data**

**Dataframe definition:**
nflId: Player identification number, unique across players (numeric)
height: Player height (text)
weight: Player weight (numeric)
birthDate: Date of birth (YYYY-MM-DD)
collegeName: Player college (text)
officialPosition: Official player position (text)
displayName: Player name (text)
