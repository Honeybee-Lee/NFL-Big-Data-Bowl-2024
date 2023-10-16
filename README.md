# NFL-Big-Data-Bowl-2024
**Overview:** <br>
American football is a complex sport, but once an offensive player receives a handoff or catches a pass, all 11 defenders focus on one task -- tackle that ball carrier as soon as possible. Conversely, the ball carrier's role is to advance the ball down the field to gain as much yardage as possible until he is tackled, scores, or runs out of bounds.<br>
<br>
This year's competition offers up a general goal — create metrics that assign value to elements of tackling. You can access the NFL’s Next Gen Stats data as in previous competitions. This year's player tracking includes data from Weeks 1-9 of the 2022 NFL season. Data will show the location, speed, and acceleration of all 22 players on the field, along with football location. Additional PFF scouting data and NFL advanced stats such as expected points and win probability are also included.<br>
<br>
Top winners will be invited to present their results to the NFL, where one team will receive an additional prize. NFL teams may also use the most useful new metrics or analysis to evaluate both their offensive and defensive players.<br>
<br>
**Examples to consider** <br>
Your challenge is generating actionable, practical, and novel insights from player tracking data corresponding to tackling. Examples include, but are not limited to:<br>
<br>
- Predictions of tackle time, probability, and/or location<br>
- Tackle range: angle of pursuit, speed and acceleration, closing speed<br>
- Player evaluation (e.g, yards saved, tackle value, missed tackles)<br>
- Credit assignment (e.g, one player makes a tackle because of another players, blocks shed, area of influence)<br>
- Tackle type (solo vs gang, open field vs in the trenches, etc)<br>
- Team and player roles and responsibilities (setting the edge, filling gaps, etc)<br>
Note that the above list is not exhaustive, and we encourage participants to be creative with their submissions.<br>
<br>
**Submission Tracks:** <br>
1. Undergraduate track. This is open only to groups or individuals composed entirely of undergraduate students. Verification may be required to prove eligibility. <br>
2. Metric track. Create a metric to assess performance and/or strategy. You may focus on offensive or defensive players, teams, or individuals.<br>
3. Coaching presentation track. This track aims to analyze and present data in a submission designed for coaches. We encourage participants interested in this track to partner with a coach (or current/former player), though this isn’t required.<br>
<br>
**Notebook requirements**
Notebooks should contain at most 2,000 words and less than ten tables/figures. Submissions will not be penalized for any number of words or figures under this limit. Participants are encouraged to show statistical code if it helps readers better understand their analyses. However, most code should be hidden in the Appendix.<br>
<br>
All notebooks submitted must be made public on or before the submission deadline to be eligible. If submitting as a team, all team members must be listed as collaborators on all notebooks submitted.<br>
<br>
Any notebook that doesn’t use the player tracking data will not be scored.<br>
<br>
This competition is specifically intended to analyze tackling strategy. Analysis of injuries resulting from tackles is not in scope for this particular project.<br>

---

### Deadline:
January 8, 2024 - Entry and Final submission deadline.<br>

---

## Data
#### Summary of data
Here, you'll find a summary of each data set in the 2024 Data Bowl, a list of key variables to join on, and a description of each variable. The tracking data is provided by the NFL Next Gen Stats team. The pff_missedTackles column in the tackles data is provided by Pro Football Focus.

#### Supplemental Data
The 2024 Big Data Bowl allows participants to use supplemental NFL data as long as it is free and publicly available to all participants. Examples of sources that could be used include nflverse and Pro Football Reference. Please note that the gameId and playId of the Big Data Bowl data merges with the old_game_id and play_id of nflverse's play-by-play data.

#### File descriptions
- Game data: The games.csv contains the teams playing in each game. The key variable is gameId.
- Play data: The plays.csv file contains play-level information from each game. The key variables are gameId and playId.
- Player data: The players.csv file contains player-level information from players that participated in any of the tracking data files. The key variable is nflId.
- Tackles data: The tackles.csv file contains player-level tackle information for each game and play. The key variables are gameId, playId, and nflId.
- Tracking data: Files tracking_week_[week].csv contain player tracking data from week number [week]. The key variables are gameId, playId, and nflId.

#### Game data
- gameId: Game identifier, unique (numeric)
- season: Season of game
- week: Week of game
- gameDate: Game Date (time, mm/dd/yyyy)
- gameTimeEastern: Start time of game (time, HH:MM:SS, EST)
- homeTeamAbbr: Home team three-letter code (text)
- visitorTeamAbbr: Visiting team three-letter code (text)
- homeFinalScore: The total amount of points scored by the home team in the game (numeric)
- visitorFinalScore: The total amount of points scored by the visiting team in the game (numeric)
#### Play data
- gameId: Game identifier, unique (numeric)
- playId: Play identifier, not unique across games (numeric)
- ballCarrierId: The nflId of the ball carrier (receiver of the handoff, receiver of pass or the QB scrambling) on the play. This is the player that the defense is attempting to tackle. (numeric)
- ballCarrierName: The displayName of the ball carrier on the play (text)
- playDescription: Description of play (text)
- quarter: Game quarter (numeric)
- down: Down (numeric)
- yardsToGo: Distance needed for a first down (numeric)
- possessionTeam: Team abbr of team on offense with possession of ball (text)
- defensiveTeam: Team abbr of team on defense (text)
- yardlineSide: 3-letter team code corresponding to line-of-scrimmage (text)
- yardlineNumber: Yard line at line-of-scrimmage (numeric)
- gameClock: Time on clock of play (MM:SS)
- preSnapHomeScore: Home score prior to the play (numeric)
- preSnapVisitorScore: Visiting team score prior to the play (numeric)
- passResult: Dropback outcome of the play (C: Complete pass, I: Incomplete pass, S: Quarterback sack, IN: Intercepted pass, R: Scramble, text)
- passLength: The distance beyond the LOS that the ball traveled not including yards into the endzone. If thrown behind LOS, the value is negative. (numeric)
- penaltyYards: yards gained by offense by penalty (numeric)
- prePenaltyPlayResult: Net yards gained by the offense, before penalty yardage (numeric)
- playResult: Net yards gained by the offense, including penalty yardage (numeric)
- playNullifiedByPenalty: Whether or not an accepted penalty on the play cancels the play outcome. Y stands for yes and N stands for no. (text)
- absoluteYardlineNumber: Distance from end zone for possession team (numeric)
- offenseFormation: Formation used by possession team (text)
- defendersInTheBox: Number of defenders in close proximity to line-of-scrimmage (numeric)
- passProbability: NGS probability of next play being pass (as opposed to rush) based off model without tracking data inputs (numeric)
- preSnapHomeTeamWinProbability: The win probability of the home team before the play (numeric)
- preSnapVisitorTeamWinProbability: The win probability of the visiting team before the play (numeric)
- homeTeamWinProbabilityAdded: Win probability delta for home team (numeric)
- visitorTeamWinProbabilityAdded: Win probability delta for visitor team (numeric)
- expectedPoints: Expected points on this play (numeric)
- expectedPointsAdded: Delta of expected points on this play (numeric)
- foulName[i]: Name of the i-th penalty committed during the play. i ranges between 1 and 2 (text)
- foulNFLId[i]: nflId of the player who comitted the i-th penalty during the play. i ranges between 1 and 2 (numeric)
#### Player data
- nflId: Player identification number, unique across players (numeric)
- height: Player height (text)
- weight: Player weight (numeric)
- birthDate: Date of birth (YYYY-MM-DD)
- collegeName: Player college (text)
- position: Official player position (text)
- displayName: Player name (text)
#### Tackles data
- gameId: Game identifier, unique (numeric)
- playId: Play identifier, not unique across games (numeric)
- nflId: Player identification number, unique across players (numeric)
- tackle: Indicator for whether the given player made a tackle on the play (binary)
- assist: Indicator for whether the given player made an assist tackle on the play (binary)
- forcedFumble: Indicator for whether the given player forced a fumble on the play (binary)
- pff_missedTackle: Provided by Pro Football Focus (PFF). Indicator for whether the given player missed a tackle on the play (binary)
#### Tracking data
Files tracking_week_[week].csv contains player tracking data from week [week].<br>
<br>
- gameId: Game identifier, unique (numeric)
- playId: Play identifier, not unique across games (numeric)
- nflId: Player identification number, unique across players. When value is NA, row corresponds to ball. (numeric)
- displayName: Player name (text)
- frameId: Frame identifier for each play, starting at 1 (numeric)
- time: Time stamp of play (time, yyyy-mm-dd, hh:mm:ss)
- jerseyNumber: Jersey number of player (numeric)
- club: Team abbrevation of corresponding player (text)
- playDirection: Direction that the offense is moving (left or right)
- x: Player position along the long axis of the field, 0 - 120 yards. See Figure 1 below. (numeric)
- y: Player position along the short axis of the field, 0 - 53.3 yards. See Figure 1 below. (numeric)
- s: Speed in yards/second (numeric)
- a: Speed in yards/second^2 (numeric)
- dis: Distance traveled from prior time point, in yards (numeric)
- o: Player orientation (deg), 0 - 360 degrees (numeric)
- dir: Angle of player motion (deg), 0 - 360 degrees (numeric)
- event: Tagged play details, including moment of ball snap, pass release, pass catch, tackle, etc (text)
![inbox_3258_820e86013d48faacf33b7a32a15e814c_Increasing Dir and O](https://github.com/Honeybee-Lee/NFL-Big-Data-Bowl-2024/assets/67603279/381d7bad-0a5e-4a7a-b0dd-a88095c3f92a)
<br>
