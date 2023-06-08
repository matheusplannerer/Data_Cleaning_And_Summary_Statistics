# Data cleaning and summary statistics

In the University of Michigan's Foundations of Sports Analytics: Data, Representation, and Models in Sports, they challenged us to explore several NHL datasets and conduct some data cleaning and preparation, while also producing summary statistics and creating graphs to understand the pattern of some variables and the relationship among them. The instructions were:

## I. Data Coding and Merging

1. Import the “NHL_Team.csv” data file and name the dataframe as “NHL_Team” in Jupyter Notebook.
a) Delete the following variables: “Unnamed:0”, “abbr”, “tname”, “lname”, and “sname”.
b) Rename the variable “name” to “team_name”.

2. Import the “NHL_competition.csv” data file and name the dataframe as “NHL_Competition” in Jupyter Notebook.
a) Delete the following variables: “Unnamed: 0”, “tz”, “start”, and “end”
b) Rename the variable “name” to “competition_name”.

3. Import the “NHL_game.csv” data file and name the dataframe as “NHL_Game” in Jupyter Notebook.
a) Delete the following variables: “X”, “period”, and “status”.

4. Merge the dataframe “NHL_Team” into the dataframe “NHL_Game” by “tid.” Continue to name the merged dataframe as “NHL_Game.”

5. Merge the dataframe “NHL_Competition” into the dataframe “NHL_Game” by “comp_id.” Continue to name the merged dataframe as “NHL_Game.”

6. In the merged “NHL_Game” dataframe, create a variable “hgd” to indicate the goal difference between home and away score (hscore – ascore) and delete observations with missing value in the variable “hgd”.

7. Drop all observations with missing values, if there is still any, from the “NHL_Game” dataframe.

8. Convert the type of the “date” variable from “object” to “datetime.”

9. Sort the NHL games by “date” and show the first 15 observations.

10. Create two dataframes that separate the “NHL_Game” dataframe by home and away games. Name them “NHL_Home” and “NHL_Away”, respectively.
a) Rename variables:
     i) For away games, rename “ascore” to “goals_for”; rename “hscore” to “goals_against”
     ii) For home games, rename “hscore” to “goals_for”; rename “ascore” to “goals_against” 
b) Create a “win” variable that equals to 1 if the team won the game; 0 if the team lost the game; and 0.5 if it was a draw. 

11. Append the “NHL_Home” and “NHL_Away” dataframes to be the new “NHL_Game” dataframe.

12. Generate a team level dataframe that aggregates the total number of games won, the total number of “goals_for” and “goals_against” for each team in each competition (i.e. grouped by tid, competition_name and type). Name this new dataframe “NHL_Team_Stats”. Make sure to convert the indexes of the new dataframe back as  variables. 

13. Create a dataframe “NHL_Game_Count” that include the total number of games played by each team in each competition (i.e. grouped by tid, competition_name and type). Name this new variable in the dataframe “game_count”.

14. Merge dataframes.
a) Merge the “NHL_Game_Count” dataframe into the “NHL_Team_Stats” dataframe by “tid”, “competition_name”, and “type”. Continue to name the merged dataframe “NHL_Team_Stats”.
b) Merge the “NHL_Team” dataframe into the “NHL_Team_Stats” dataframe by “tid”. Continue to name the merged dataframe “NHL_Team_Stats”.

15. Import the “pp.pk.ppgf.csv” data file and name the dataframe as “NHL_PPPK” in Jupyter Notebook. Merge the “NHL_PPPK” dataframe into the “NHL_Team_Stats” dataframe by “tricode” and “competition_name”.

16. Create new variables in the “NHL_Team_Stats” dataframe.
a) Winning percentage (“win_pct”)=”win”/ total number of games played
b) Average goals for per game (“avg_gf”)=total number of goals for / total number of games played     
c) Average goals against per game (“avg_ga”)=total number of goals against / total number of games played

17. In the “NHL_Competition” dataframe, the variable “type” indicates the type of competition: type=2 – regular season. Create a dataframe that contains team statistics for games only during regular seasons. Name this dataframe “NHL_Team_R_Stats”. 

## II. Calculating Summary Statistics
1. In the “NHL_Game” dataframe, calculate summary statistics for the  “goals_for” variable; calculate summary statistics for the “goals_against” variable based on whether it is home or away game.

2. Create a histogram of the “goals_against” variable by whether the game is home or away 
a) Make the color of the histogram green
b) Set the number of bins to be 20
c) Make sure the two sub-histograms share the same ranges for the x-axis and y-axis.

## III. Correlation Analyses
1. In the “NHL_Team_R_Stats” dataframe, make a scatter plot to depict the relationship between the total number of goals for and the winning percentage. 
a) Plot the total number of goals for on the x-axis and winning percentage on the y-axis.
b) Add a regression line to the scatter plot.
c) Make the title of the graph “Relationship between Goals for and Winning Percentage” and make the font size 11.
d) Label the x-axis “Total Goals for” and label the y-axis “Winning Percentage”.

2. In the “NHL_Team_R_Stats” dataframe, calculate the correlation coefficient between total number of goals for and winning percentage.

3. Create a scatter plot of the total number of goals for and winning percentage similar to step 1 for regular season games. In this graph, group observations by “competition_name”.
a) Plot the total number of goals for on the x-axis and winning percentage on the y-axis.
b) Add a regression line to the scatter plot.
c) Make the title of the graph “Relationship between Goals for and Winning Percentage” and make the font size 11.
d) Label the x-axis “Total Goals for” and label the y-axis “Winning Percentage”.

4. For the “NHL_Team_R_Stats” dataframe, delete observations of 2011 and 2012 seasons. Continue to name the dataframe “NHL_Team_R_Stats”.

5. In the new “NHL_Team_R_Stats” dataframe, create a scatter plot of total number of goals for and winning percentage.
a) Plot the total number of goals for on the x-axis and winning percentage on the y-axis.
b) Add a regression line to the scatter plot.
c) Make the title of the graph “Relationship between Goals for and Winning Percentage” and make the font size 11.
d) Label the x-axis “Total Goals for” and label the y-axis “Winning Percentage”.

6. Calculate the correlation coefficient between total number of goals for and winning percentage in the updated “NHL_Team_R_Stats” dataframe.

7. Save dataframes as csv files. 
a) Name the updated “NHL_Game” dataframe as “NHL_Game2”.
b) Name the “NHL_Team_Stats” dataframe as “NHL_Team_Stats”.
c) Name the “NHL_Team_R_Stats” dataframe as “NHL_Team_R_Stats”.
d) Make sure to exclude the index as a column in the csv files.
