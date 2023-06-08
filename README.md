# Data cleaning and summary statistics

Exploring several NHL datasets and conduct some data cleaning and preparation, while also producing summary statistics and creating graphs to understand the pattern of some variables and the relationship among them. 

I. Data Coding and Merging

Import the “NHL_Team.csv” data file and name the dataframe as “NHL_Team” in Jupyter Notebook.
a) Delete the following variables: “Unnamed:0”, “abbr”, “tname”, “lname”, and “sname”.
b) Rename the variable “name” to “team_name”.

Import the “NHL_competition.csv” data file and name the dataframe as “NHL_Competition” in Jupyter Notebook.
a) Delete the following variables: “Unnamed: 0”, “tz”, “start”, and “end”
b) Rename the variable “name” to “competition_name”.

Import the “NHL_game.csv” data file and name the dataframe as “NHL_Game” in Jupyter Notebook.
a) Delete the following variables: “X”, “period”, and “status”.

Merge the dataframe “NHL_Team” into the dataframe “NHL_Game” by “tid.” Continue to name the merged dataframe as “NHL_Game.”

Merge the dataframe “NHL_Competition” into the dataframe “NHL_Game” by “comp_id.” Continue to name the merged dataframe as “NHL_Game.”

In the merged “NHL_Game” dataframe, create a variable “hgd” to indicate the goal difference between home and away score (hscore – ascore) and delete observations with missing value in the variable “hgd”.

Drop all observations with missing values, if there is still any, from the “NHL_Game” dataframe.

Convert the type of the “date” variable from “object” to “datetime.”

Sort the NHL games by “date” and show the first 15 observations.

Create two dataframes that separate the “NHL_Game” dataframe by home and away games. Name them “NHL_Home” and “NHL_Away”, respectively.
a) Rename variables:
     i) For away games, rename “ascore” to “goals_for”; rename “hscore” to “goals_against”
     ii) For home games, rename “hscore” to “goals_for”; rename “ascore” to “goals_against” 
b) Create a “win” variable that equals to 1 if the team won the game; 0 if the team lost the game; and 0.5 if it was a draw. 

Append the “NHL_Home” and “NHL_Away” dataframes to be the new “NHL_Game” dataframe.

Generate a team level dataframe that aggregates the total number of games won, the total number of “goals_for” and “goals_against” for each team in each competition (i.e. grouped by tid, competition_name and type). Name this new dataframe “NHL_Team_Stats”. Make sure to convert the indexes of the new dataframe back as  variables. 

Create a dataframe “NHL_Game_Count” that include the total number of games played by each team in each competition (i.e. grouped by tid, competition_name and type). Name this new variable in the dataframe “game_count”.

Merge dataframes.
a) Merge the “NHL_Game_Count” dataframe into the “NHL_Team_Stats” dataframe by “tid”, “competition_name”, and “type”. Continue to name the merged dataframe “NHL_Team_Stats”.
b) Merge the “NHL_Team” dataframe into the “NHL_Team_Stats” dataframe by “tid”. Continue to name the merged dataframe “NHL_Team_Stats”.

Import the “pp.pk.ppgf.csv” data file and name the dataframe as “NHL_PPPK” in Jupyter Notebook. Merge the “NHL_PPPK” dataframe into the “NHL_Team_Stats” dataframe by “tricode” and “competition_name”.

Create new variables in the “NHL_Team_Stats” dataframe.
a) Winning percentage (“win_pct”)=”win”/ total number of games played
b) Average goals for per game (“avg_gf”)=total number of goals for / total number of games played     
c) Average goals against per game (“avg_ga”)=total number of goals against / total number of games played

In the “NHL_Competition” dataframe, the variable “type” indicates the type of competition: type=2 – regular season. Create a dataframe that contains team statistics for games only during regular seasons. Name this dataframe “NHL_Team_R_Stats”. 
