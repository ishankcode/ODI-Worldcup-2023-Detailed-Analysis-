# ODI-Worldcup-2023-Detailed-Analysis-
Scraped the Last 5 years' ODI data to analyze the best batsmen, and bowlers as well as build the best playing 11 for each team.



----
# Introduction to Sport "CRICKET"
Cricket is a game of bat-and-ball where teams take turns to bat and field. The goal of the game is to score maximum runs while restricting the opposite team (trying to
get the opposing team out) to as minimum runs as possible. In the End team with the Most runs won. There are three formats of the Game which are Test (4 innings (two for each team spread over a period of 5 days)), ODI (Lmited 50 Over format), T20 (Limited 20 over format).
This Analysis is focused on ODI (50 Over format) because cricket's biggest tournament is supposed to be held in October in INDIA.
The Project is Divided into 3 Phases:
1. Web Scraping
2. Data Modelling
3. Data Visualization in Tableau

## Part -1  Web Scraping ( Python - Pandas, Beautiful Soup, Selenium, Excel)
To analyze the best team, batsmen, and bowlers for the 2023 World Cup I decided to focus on player's performance in the Last 5 years. 
I performed the scraping in the following steps:
![image](https://github.com/ishankcode/ODI-Worldcup-2023-Detailed-Analysis-/assets/66678343/17ce42cd-cb66-49bf-b851-acfd49649b50)
![image](https://github.com/ishankcode/ODI-Worldcup-2023-Detailed-Analysis-/assets/66678343/ecf5b9f9-6fbb-4c49-bfb3-6584933d53cf)

## Part-2 Data Modelling (Python - Pandas, Numpy, Excel)
For specific Tableau Visuals which have specific requirements analyzed and merged data (Performed data engineering) to get data in the desired form for example:
1. To create a Jitter plot in Bowling Analysis (Please see Tableau Dashboard) I needed to normalize and then rank each player based on 4 Bowling Metrics which are
Wickets Taken (A higher Value is Better), Bowler's Economy (LOower Value means a Higher rating), Boundary % (A lower value is Better), and Extras Given (Wide + Noballs,
Lower Value is Better). Check Bowling_scorecard_modify notebook

2. For Building the Best Playing 11 for each team created the best squad for different situations such as -
   - Balanced : 5 Batsmen + 3 Allrounders + 3 Bowlers
   - Bowling Max: 5 Batsmen + 2 Allrounders + 4 Bowlers
   - Batting Max: 6 Batsmen + 2 Allrounders + 3 Bowlers
   - Batting Super: 6 Batsmen + 3 Allrounders + 2 Bowlers
   - MY BEST: Based on my knowledge and intuition
  
To create such a detailed analysis I had to rank each player within the subgroup for each nationality i.e. for example created a ranking of all bowlers for team India so that if there is a requirement for Balanced formation I can easily select the top 3 Bowlers.
To create such a ranking I explored 2 options:
- Ranking based on assigning weights to various factors that are important to that group (playing role) example batting average, and strike rate for batsmen. The weights in this method were decided based on my knowledge of cricket.
- Used Logistics regression to create a model of the coefficients of the factors for each group (basically used logistic regression to classify players based on their role - while deciding ranking coefficients for Top order Batsmen - logistic regression has to output Class "Top Order Batsment and second class "Others").

After the ranking had been created, created the best playing 11 for any of the squads mentioned above.

## Part-3 Data Visualization (Tableau, Excel)
Created 3 main Dahboards:
### 1. Batting Analysis (Cansist of 3 main Views):
   - Scatter plot for Total Runs Vs Num of Matches ( Highlighting top 10,15, 20 Players).
   - Detailed Table for identifying Top batsmen based on other criteria as well.
   - 3rd Plot is to analyze & emphasize the Player's Performances in their most recent matches (Yellow for the most recent, red for the Last 5 matches).
![image](https://github.com/ishankcode/ODI-Worldcup-2023-Detailed-Analysis-/assets/66678343/19ca2f89-e649-4266-909e-f823ecd5143d)


### 2. Bowling Analysis:
  - Jitter plot - Provide a filter (Parameter) to select and analyze player's performances across 4 bowling metrics (Wickets, Extras GiveN, Boundary %, Avg. economy) as well as compare the player and rank them against other players.
  - Second view describes the Best 5 Best bowlers in the last 5 years across other categories such as Most 5 wickets taken in a single match, Most MAIDEN OVERS, BOWLING AVERAGE, and bowling economy.
![image](https://github.com/ishankcode/ODI-Worldcup-2023-Detailed-Analysis-/assets/66678343/4e4fcf80-b80a-4cf0-98cd-437eae5a44bf)


### 3. Building Best Playing 11 (Important details):
  -  Can build the best 11 for all the 10 teams qualified for the world cup as well as across various different squads.
  -  Widget highlights the team's combined performance such as Probable score, Avg economy (basically saying the average score opposition can make against them), as well as bowling average.
  -  The captain of the team is marked with (c) as well as player's playing role can be analyzed based on the symbol of Ball (Bowler), Bat (Batsmen), gloves (Wicketkeeper), ball+bat (allrounder).
  -  Win-loss %, as well as current ODI ranking and number of times the world cup won is highlighted for each team.
  - Running a sum bar graph is useful to analyze the team's performance across the past 5 years as well as for identifying the maximum winning streak.

![image](https://github.com/ishankcode/ODI-Worldcup-2023-Detailed-Analysis-/assets/66678343/04e2fcb0-e3be-49c9-be4c-c8a59bdb6137)

-----
### Link to Tableau Dashboard :
https://public.tableau.com/app/profile/ishank.gupta1043/viz/CricketAnalysisOdiWorlcup2023/HomePage#1

  
