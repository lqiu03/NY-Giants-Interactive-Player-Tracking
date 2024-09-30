# NY-Giants-Interactive-Player-Tracking
10 frames per seconds player tracking for NY Giants 2021-22 offensive play-calling 

**Files giants_all_players_movement.zip contains player tracking data from 2021-22 NFL Season NY Giants Week 1-8.**

# Data Dictionary
---

## Movement Data

**Description:** This dataset contains player movement information captured during NFL games, including positions, speeds, and events at each frame of a play.

### Dataframe Definition:

- **`gameId`** (`numeric`): Unique game identifier.
- **`playId`** (`numeric`): Play identifier, not unique across games.
- **`nflId`** (`numeric`): Player identification number, unique across players. When the value is `NA`, the row corresponds to the ball.
- **`frameId`** (`numeric`): Frame identifier for each play, starting at 1.
- **`time`** (`datetime`): Timestamp of the play (`yyyy-mm-dd hh:mm:ss`).
- **`jerseyNumber`** (`numeric`): Jersey number of the player.
- **`club`** (`text`): Team abbreviation of the corresponding player.
- **`playDirection`** (`text`): Direction that the offense is moving (`"left"` or `"right"`).
- **`x`** (`numeric`): Player position along the long axis of the field (0 - 120 yards).
- **`y`** (`numeric`): Player position along the short axis of the field (0 - 53.3 yards).
- **`s`** (`numeric`): Speed in yards per second.
- **`a`** (`numeric`): Acceleration in yards per second squared.
- **`dis`** (`numeric`): Distance traveled from the prior time point, in yards.
- **`o`** (`numeric`): Player orientation in degrees (0 - 360 degrees).
- **`dir`** (`numeric`): Angle of player motion in degrees (0 - 360 degrees).
- **`event`** (`text`): Tagged play details, including moments like ball snap, pass release, pass catch, tackle, etc.

---

## PFF Scouting Data

**Description:** This dataset provides scouting information from Pro Football Focus (PFF), detailing player roles, positions, and performance metrics during plays.

### Dataframe Definition:

- **`gameId`** (`numeric`): Unique game identifier.
- **`playId`** (`numeric`): Play identifier, not unique across games.
- **`nflId`** (`numeric`): Player identification number, unique across players.
- **`pff_role`** (`text`): The player's role on this play. Possible values:
  - `Coverage`: Defensive player whose initial goal is to play man or zone coverage.
  - `Pass`: Offensive player identified as the passer.
  - `Pass block`: Offensive player fully blocking a defender from the QB or in a clear pass block stance.
  - `Pass route`: Offensive player not identified as a Pass Blocker or Passer.
  - `Pass rush`: Defensive player whose initial intent is to rush the passer.
- **`pff_positionLinedUp`** (`text`): Position the player was aligned at the snap of the ball on this play.
- **`pff_hit`** (`binary`): Indicator (0 or 1) if a defensive player is credited with recording a hit on this play.
- **`pff_hurry`** (`binary`): Indicator if a defensive player is credited with recording a hurry on this play.
- **`pff_sack`** (`binary`): Indicator if a defensive player is credited with recording a sack on this play.
- **`pff_beatenByDefender`** (`binary`): Indicator if a blocking offensive player is beaten by a defender but not charged for yielding a hit, hurry, or sack.
- **`pff_hitAllowed`** (`binary`): Indicator if a blocking offensive player is responsible for a hit on the QB.
- **`pff_hurryAllowed`** (`binary`): Indicator if a blocking offensive player is responsible for a hurry on the QB.
- **`pff_sackAllowed`** (`binary`): Indicator if a blocking offensive player is responsible for a sack on the QB.
- **`pff_nflIdBlockedPlayer`** (`numeric`): If the player is a blocking offensive player, the `nflId` of the first defender they blocked.
- **`pff_blockType`** (`text`): The type of block executed by a blocking offensive player. Possible values:
  - **`BH`**: Backfield Help - A block from a player aligned in the backfield helping on a block.
  - **`CH`**: Chip Block - Players who chip a pass rusher when they release for their route.
  - **`CL`**: Second Level – A block made at the second level, at least two yards across the line of scrimmage.
  - **`NB`**: No Block - When a blocker executes no block but runs their path or takes their pass set.
  - **`PA`**: Play Action Pass Protection - A blocker pass protecting inline on a play action pass.
  - **`PP`**: Pass Protection - A standard pass protection block from an inline blocker.
  - **`PR`**: Pocket Roll Block - Used when the offense executes a "rolling pocket."
  - **`PT`**: Post Block - A post block by an offensive player in pass protection.
  - **`PU`**: Backfield Pickup - A pass protection pickup by a player aligned in the backfield.
  - **`SR`**: Set & Release - A blocker who sets to pass protect a defender before releasing.
  - **`SW`**: Switch Block - A blocker who passes off (or attempts to pass off) a defender.
  - **`UP`**: Pull Pass Protection - A blocker pulling in pass protection from an inline alignment.
- **`pff_backFieldBlock`** (`binary`): Indicator if the block by an offensive player occurred in the offensive backfield.

---

## Player Data

**Description:** This dataset contains biographical and physical information about NFL players.

### Dataframe Definition:

- **`nflId`** (`numeric`): Player identification number, unique across players.
- **`height`** (`text`): Player height (e.g., `"6-2"` for 6 feet 2 inches).
- **`weight`** (`numeric`): Player weight in pounds.
- **`birthDate`** (`date`): Date of birth (`YYYY-MM-DD`).
- **`collegeName`** (`text`): Name of the college the player attended.
- **`officialPosition`** (`text`): Official position of the player (e.g., `QB`, `WR`, `LB`).
- **`displayName`** (`text`): Player's full name.

---

## Field Diagram Reference

For position fields `x` and `y` in the Movement Data:

- The field is 120 yards long (including end zones) and 53.3 yards wide.
- **`x`**: Measures the position along the length of the field (0 to 120 yards).
- **`y`**: Measures the position across the width of the field (0 to 53.3 yards).

![Football Field Diagram](https://raw.githubusercontent.com/yourusername/yourrepository/main/images/field_diagram.png)

*(Note: Include an actual image of the football field with axes labeled for clarity.)*

---


## Contact Information

For any questions or issues related to the data:

- **Maintainer:** Lucas Qiu
- **Email:** lqiu03@UCLA.EDU


# Contributing

Contributions to improve the datasets or documentation are welcome. Please open an issue or submit a pull request.

---

# Acknowledgments

- Original raw data was downloaded from NFL Big Data Bowl and was re-structured for this project.

---

# Disclaimer

This data is intended for educational and research purposes ONLY.
