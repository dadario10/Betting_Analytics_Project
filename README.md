# Betting_Analytics_Project
To analyze betting data and find trends

## Objective
Who would you place an online bet on in the NFL?

## Project Description
With technological advancements throughout the past decade, online sports betting has become extremely accessible and convenient to those who wish to place wagers. As of 2021, the online sports gambling industry had a market value of nearly $75.5 Billion, and a revenue forecast of $205 Billion by 2030. Another main attraction to the concept is variety. Online betting sites offer a wide selection of sports and markets to chose from, but how do you navigate them? For beginners, placing a wager through an online site or app can seem intimidating. This project has been designed to aid in making an informed bet and our group will describe the basics for understanding the terminology and concepts used.

## Table of Contents
- [Initial_Process](#initial_process)
- [Stadium Type Analysis](#stadium_type_analysis)
- [Over/Under Analysis](#over_under_analysis)
- [Resources](#resources)

## Initial Process
We began by researching and collecting existing datasets online to form csv files to be able to extract data for NFL Teams, scoring history, stadium locations and betting history. Once the correct files were located, cleaning the data on Python and creating one data frame that would be used for all the categories covered in the assignment. 

![image](https://github.com/dadario10/Betting_Analytics_Project/assets/130397259/48f44fbf-1fa7-4662-bd7d-ce6e3b735b27)

## Over Under Analysis
###by: Brettney Chau-Dang
One of the most common types of over/under bet is placed on the combined score of the two teams playing in the game.
The concept of betting on totals, or better known as over/under, in the NFL, comprises of wagers being placed on the total amount of points scored within a game. The goal is to choose from two options, where the score will be higher or lower than a pre-determined number set by the corresponding sportsbook being used. 
If a game exceeds regular game time play, overtime will be included. If the outcome of the total points for the game falls exactly on the quoted line/pre-determined value, the total is then declared as a "push", in which all wagers are returned to the bettors.
I first had to calculate the total number of games that were played for the last 10 NFL seasons.

![image](https://github.com/dadario10/Betting_Analytics_Project/assets/130397259/87d9c7ac-8afa-4bb8-ad7e-19ccb74bc3c1)

To determine whether the status of a game came in Over or Under the quoted line, I created a formula to populate the result in a new column.

![image](https://github.com/dadario10/Betting_Analytics_Project/assets/130397259/7670980a-f517-4a4c-8b4d-af9528abeeeb)
 
From there, I extracted the columns I needed for my bar chart and renamed the columns accordingly.
Over/Under by Season
From the original data frame created, I filtered the data into a new data frame only consisting of the columns needed for my analysis. 
Once I had narrowed down the columns I needed, I then created a column that would calculate the total score of each game that was played. I then was able to determine the status of whether that game was higher or lower than the pre-determined value from the over under line.

![image](https://github.com/dadario10/Betting_Analytics_Project/assets/130397259/bc5dc9bf-bd4f-4e4a-8c97-30a90c9f611b)

Once that information was filtered, I created a bar chart to showcase the total games that had fallen over or under for each NFL Season from 2013 to 2022. Based on this analysis I would bet under the quoted line for any given game, because nearly 60% of all games played were Under.
 
![image](https://github.com/dadario10/Betting_Analytics_Project/assets/130397259/23e6799b-622d-4d8c-bc43-a34098e304a4)
 
Over/Under by Team
There are currently 32 Teams in the NFL. After filtering through the data and creating a bar chart, there were a couple NFL Teams that stood out. For example, the Kansas City Chiefs fell Under the quoted line in a total of 58 games over the last 10 seasons. If they were playing, I would place my bet in the Under category. 

![image](https://github.com/dadario10/Betting_Analytics_Project/assets/130397259/09d454f6-dd48-40e8-894d-e1c116d2f041)

![image](https://github.com/dadario10/Betting_Analytics_Project/assets/130397259/b815e800-9855-4e22-ab5e-9d71f59d7575)

However, the New England Patriots, Philadelphia Eagles, and the Las Vegas Raiders (previously known as the Oakland Raiders), which changed cities as of 2019, all had a total of 50 games that were all Over the quoted line. Ironically, the Las Vegas Raiders also had the lowest number of total games that were Under the quoted line. If the Las Vegas Raiders were playing In the game, I would likely place a bet in the Over category.

![image](https://github.com/dadario10/Betting_Analytics_Project/assets/130397259/beeb20f4-4eb4-4ee0-a595-2e5a23ff4483)

## Stadium Type Analysis
### By: Justin Butler
 
For my section of our project, I chose to analyze how betting on an NFL game may be affected by the type of stadium the games are played in. Whether games played indoors in dome style stadiums are approached differently than games played outdoors in open-air style stadiums. Considering that harsher weather generally plays a factor on games by making it harder for teams to score. For e.g.: High wind speeds making it harder for the quarterbacks to throw to their receivers or more difficult for kickers to kick field goals and extra points after touchdowns.  From this topic I will analyze our group’s acquired data from the 2013 to 2023 NFL seasons and pose two more precise questions and in my conclusion make a recommendation on how I would bet on a future NFL game. Now let’s get into the data!

**Question 1) –  Is stadium type, being either indoor or outdoor factored in when the over/under line is set for games ?**
    To answer my questions I first used the value.counts() function on the stadium column in our csv data file, which contained the names of all the stadiums played in over the past 10 years to get the full stadium list so I could later filter it by indoor and outdoor and place these values in a newly created column titled “stadium_type”.  I used the following for loop to achieve the desired result:
 ![image](https://github.com/dadario10/Betting_Analytics_Project/assets/129707393/361d2830-084f-4725-8af0-8826671863a4)
    With this new data column, I could now analyze all the rest of the data from the csv file through the prism of games played indoors and outdoors. For instance, the below summary statistics table of the tracked weather metrics for all the games to provide some evidence for my consideration of weather being a large factor on outdoor games opposed to indoor games. Achieved by performing the groupby() and aggregation (agg([“mean”, “median”, “var”, “std”, “sem”])  functions on the stadium_type column against the 3 weather columns for temperature, wind and humidity.
Weather Summary Statistics Table:
![image](https://github.com/dadario10/Betting_Analytics_Project/assets/129707393/d001aeb5-9cbf-4e0f-a92d-c506b6a7ca48)
    The table supports the idea that the weather in outdoor stadiums is much harsher and unpredictable than indoor stadiums with such high statistic measurements such as variance and standard deviation. With an outdoor temperature variance 30 times greater than indoor temperatures, a standard deviation almost 6 times greater than indoor, outdoor wind speed variance almost 10 times greater than indoor and standard deviation almost 3 times greater, the analysis clearly shows tremendous variability and value spread across the weather data. Meaning the overall weather at outdoor stadiums can be significantly different than indoor stadiums due to things like changing weather conditions, time of year and geography. 

   To answer Question 1) better I formed the following hypotheses:
* Alternative Hypothesis: If stadium type is factored into how the over/under lines are set. Then the average over/under line for games played indoors should be higher than the games played outdoors. 
* Null Hypothesis: If stadium is NOT factored into how the over/under lines are set. Then the average over/under line for games played indoors will NOT be higher than the games played outdoors.
    To answer these and see how the stadium type affects a betting measure such as over/under through statistical analysis I again used the groupby() and aggregation  functions to analyze the over/under line of each game against the stadium type. To produce the following summary statistics table:
![image](https://github.com/dadario10/Betting_Analytics_Project/assets/129707393/41bf6529-d764-4f53-b5da-ba377572c351)
    To visualize the data between these 2 columns and the summary table I chose a box-and-whisker plot for its ability to show mean, quartiles, outliers and overall potential skew of the data. Seen below:
![image](https://github.com/dadario10/Betting_Analytics_Project/assets/129707393/efccc2ec-a07b-45f2-bdd1-fa739d4f800b)
    Once plotted I was able to see what was also displayed by the weather summary statistics table, a much higher degree of spread in the Outdoor values than the Indoor values. Shown by one example, with the much higher number of outliers in the Outdoor values than the Indoor Values. This finding makes sense in connection with the weather analysis: much more variability in the potential weather during Outdoor games ties into the concept of much more variability in over/under lines set for Outdoor games. For e.g., a very snowy and windy game likely will have a lower over/under line than a sunny game with little wind. It also shows the in a clear visual sense that the Indoor mean is higher than the Outdoor mean.
    To test my hypotheses, I performed an independent 2-sample T-test as I was comparing 2 distinct groups, the over/under lines of games played indoor versus those of games played outdoors.
![image](https://github.com/dadario10/Betting_Analytics_Project/assets/129707393/e3a4ee5f-c1c5-463d-945d-ba0d44060588)
    This produced an extremely low P-value, assuring a very high confidence level and proving what my alternative hypothesis stated. That the average over/under line of Indoor stadiums is higher than that of Outdoor stadiums. Allowing us to at least assume that the stadium type in some capacity is factored in when the over/under lines are set for games. Although it is important to note that, due to the extensive data and other factors considered by those who set these betting over/under lines, my results thus far are not enough for me to make a definitive statement for or against our original question, only a recommendation leaning towards a small correlation to stadium type playing a factor. 

**Question 2)  - Is there a homefield advantage to teams playing their home games indoors versus outdoors ?**
    To analyze this question, I used another for loop to iterate through the “score_home” and “score_away” columns and count the column with the higher value as the “game_winner”. Whose value would be then stored in the newly created column of the same name with the same 3 letter abbreviation as seen in the “team_home” or “team_away” columns.
![image](https://github.com/dadario10/Betting_Analytics_Project/assets/129707393/b6c2a1c2-0d97-49a3-a267-2c1e6b72fe34)
The next step was to determine if the home team won, this was done by creating a new column titled “home_team_won” and applying the anonymous “lambda” function to it by comparing the values of the “team_home” and “game_winner” columns row by row. When the two values are the same then that means the home team won that game, and a 1 is placed in the “home_team_won” column. If the away team won then a 0 is placed. 1s and 0s are used here so I can later divide the total column sum() of the “home_team_won” column by the count() (tota)l of it. As seen below.
![image](https://github.com/dadario10/Betting_Analytics_Project/assets/129707393/fcd27b82-a4bf-4861-b063-5b6059bd4573)
Which produced a nice clean DataFrame:
![image](https://github.com/dadario10/Betting_Analytics_Project/assets/129707393/bdf04f06-fc8d-4a16-9b12-3568ac5b3c11)
    To visualize this data, I chose a simple bar plot. I felt this was the best choice as the 2 vertical bars this would create, one displaying the percentage of home games won by NFL teams whose home field is Indoors and the other showing home games won by NFL teams whose home fields are outdoors, would allow for easy visual comparison of the percentage values, thus any potential conclusions could be easily drawn.
![image](https://github.com/dadario10/Betting_Analytics_Project/assets/129707393/7cbe0a63-fb54-4827-97c7-ccbb2811c066)
    Important to note that most teams in the NFL play in Outdoor Stadiums. Only 10/32 teams have Indoor Stadiums for their home fields as of 2023. This can be reflected in the data as 1983 of the 2707 games in the csv data were played in Outdoor stadiums over the past 10 seasons. Even still, the bar plot shows a very even playing field (no pun intended) over the past 10 seasons worth of games. With game data recorded over thousands of games, the comparison of the 2 values reveals almost identical percentages at 54% and 56% respectively. The data and subsequent bar plot show more of a skew towards home teams in general having an advantage than an advantage to the stadium type the home teams play in. The corresponding data to these figures would mean 46% of teams have lost their away games that they played indoors and 44% of away teams have lost games played in Outdoor stadiums. Therefore, I must conclude that I see no significant correlation towards a home field advantage for either home stadium type. The slight 2% higher value for the Outdoor stadium teams can be mostly nullified by the fact that there have been 2.73 times more Outdoor games than Indoor games over the past 10 seasons, a slightly higher value is not a surprise or statistically significant given the size discrepancy in games played Outdoor vs. Indoor.

### CONCLUSION & LIMITATIONS:
   After all this analysis, I believe I can make some modest recommendations towards placing a bet on an NFL game based on the stadium type the game is played in. First,  I would advise betting on the over/under line opposed to placing a bet on one team to win over the other. Based on some positive correlation results towards over/under line based on stadium type. Whereas no real correlation was found on a home field advantage. When making your bet I would look for 2 things based on my findings, expected weather for the game and corresponding stadium type. Based on the extreme variability I uncovered with the weather of outdoor NFL games and the data I found on average over/under lines. I would look for games with poor expected weather that will be played outdoors and bet the games point total to be under the over/under line for example.
    Some limitations to my analysis include:
*	Overall data limitations, I originally chose to examine growth in the NFL betting industry and was going to try to predict future growth in the market based on my findings. Although I was unable to find any accessible or clean data. 
*	Data limitations in the data my group found. Several rows in the weather columns possessed Nan values and limited the scope of this section of data. For ex: more data in the “weather_detail” column such as rainy or sunny for example could have allowed for more in-depth analysis. E.g., average score for games labeled as rainy vs. sunny. 
*	Ability/Time constraints. Due to the need to change project topics, a few days were lost at the beginning of the project timeline. Also, my experience in Data Analytics limited my ability to analyze our csv data, or any data for that matter, at a more detailed level. In the future with more skills such as “data scrapping” more detailed data from multiple sources would likely be available, thus allowing for a more detailed analysis.

## Moneyline Betting: Analysis and Conclusion
### By: Dario Micucci

In football, the Moneyline is the type of sports bet in which you predict the outcome of the game based on the outright winner. You simply select which team you think will win the game. The Moneyline will show 2 teams, the respective odds will have either a ‘-’ or a ‘+’ next to the lines. The negative number indicates the favorite, while the positive number represents the underdog. The negative number shows how much you would need to wager in order to make $100. For example, if the number is -190, you would need to wager $190 to make $100. The positive however shows how much additional money your bet would make if you wager $100. For example, if the line is +160 you stand to make and additional $160 on your $100 wager. The greater the negative number the more favoured that team is while simultaneously the greater positive number shows how great of an underdog the other team is. 
In order to obtain the data that I required I used the data set one of my collogues provided and cleaned it up. I narrowed our window to the years 2013-2022 first in the “nfl_scores.ipynb” file. Then I changed all the team names so the individual columns matched and would be easier to draw information from. In the “nfl_favorite_win.ipynb” file I then collected the data and created new columns for categories that I would need to answer my question about Moneyline. Once I created the “favorite_win” and “home_win” columns I had all the information I needed. I pulled information from those columns to find averages for favorite win, home win, and underdog win. I used value_counts to find the total wins for each column as well. At this point I had the information I needed to answer my question.
Question: Is betting the favourite in Moneyline a good betting strategy?
Analysis and numbers: Our dataset collected NFL games spanning from 2013 to 2022. During this time there was 2707 games played. After cleaning the data I found that 65.79% of the time the favourite team did win the game. The favourite team won 1781 out of the possible 2707 games. The underdog only won 926 times out of 2707 for a win percentage of 34.21%. This shows that a vast majority of the time the moneyline favourite did in fact win the game. I tested to see if there was any correlation with the home team winning but the home team only won 1502 times for a win percentage of 55.49%. This tells me that the home team is not always the favoured team in football and following the moneyline gives the gambler a greater chance of picking the correct winner as apposed to simply picking the home team to win.
![favoured](https://github.com/dadario10/Betting_Analytics_Project/assets/130175420/a12a05a2-44d8-4bb1-8277-1cfc5577c42b)
 “Favoured Winner by Season” bar chart shows how many times the moneyline was right per week by year. By looking at this graph there is no clear pattern week to week. So only betting certain weeks does not give the gambler a better chance of winning their bets. This shows that in order to get the full benefits of the 65.79% winning rate, the gambler but be consistent in their bets because that is how they can win in the long run. 
 ![weekcount](https://github.com/dadario10/Betting_Analytics_Project/assets/130175420/4854be8c-c241-4390-81d7-203df3947a91)
![linevisualization](https://github.com/dadario10/Betting_Analytics_Project/assets/130175420/2d7fe7bf-380c-47b1-b799-87dfc0c88f03)
The graphs, “Weekly Count By Season” and “Weekly Count by Season Line Graph” show the total number of games played per week. In the bar chart you can see some weeks have the maximum number of games which is 16 and the lowest number of games which is 1. Looking specifically at week 18, you can see a gap in the bar chart from 2013-2020. This is because the NFL added week 18 to their schedule for the first time in 2021. This now gives more opportunity for gamblers to make bets and going forward gives more data to run and see if the moneyline win percentage goes up or down. Looking at the bar chart and line plot you can see and in 2020-2022 the NFL increased the number of ‘Wildcard’ games from 4 to 6. This also going forward will add more data to work with and potentially increase the success rate of betting with the moneyline.
Conclusion and Limitations: Based on the data we worked with, betting on the moneyline will often give you a winning result on your gambling picks. The only possible limitation to this is the odds. If the odds don’t give a great return, as is explained above, then the favourite losing 34.21% of the time may not cover the amount you have to gamble in order to win in the long run. More data is required based on average odds that can be connected to the findings in the report to come up with more information. 









## Resources
### 1) Real-time sports data API
 As one of the resources, "https://sportsdata.io/developers/api-documentation/nfl#" was used to extract data using an API key. Which provided access to NFL metadata, live odds feeds, predictions, settelements and results, splits, matchups, trends, active sportsbooks and many more that can be sorted and categorized by team, game date, game season (pre,regular&post), market ID, market type, event, player stats, team stats and many more.
### 2) nflgame v.1.2.20
An API used to retrieve and read NFL Game Center Json data was nflgame "https://pypi.org/project/nflgame/".
This python extension works by parsing the same JSON data that powers NFL.com's live GameCenter, which means it can be used to report game statistics while a game is being played.
### 3) NFL Teams
An exisiting .csv file dataset for NFL Teams was found on "https://www.kaggle.com/datasets/tobycrabtree/nfl-scores-and-betting-data". This dataset consisted of all 32 NFL team names, ID's, conferences and divisions.
### 4) Game Score History
An existing .csv file dataset was found on www.kaggle.com, owned by SpreadSpoke. This dataset consisted of NFL football games since the 1966 season with game results and descriptive info including if a playoff game, played at a neutral site, and weather information if available. 
### 5) NFL Stadiums
An exisiting .csv file dataset was found on www.kaggle.com. This dataset consisted of NFL Stadium information, past and present. 
### 6) Other sources
https://github.com/jp-wright/nfl_betting_market_analysis
https://github.com/peanutshawny/nfl-sports-betting/tree/master
https://www.fanduel.com/sports-betting-strategy/
https://www.nationalfootballpost.com/how-to-bet/over-under-betting/
https://tenor.com/search/hungergames-gifs
https://madeinca.ca/gambling-canada-statistics/
https://www.forbes.com/sites/greatspeculations/2023/02/13/as-sports-bettings-popularity-rises-in-the-us-keep-in-mind-that-its-not-a-replacement-for-investing/?sh=4abaeda6d09a

