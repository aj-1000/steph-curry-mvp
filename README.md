# METHODOLOGY: Evaluating the shooting in Steph Curry's 2015-16 MVP season relative to both his career and the greatest shooting seasons of all time.
[Blog post](https://lobcitydata.blogspot.com/2018/09/steph-curry-mvp.html)
## Data Collection
First, [Basketball Reference](https://www.basketball-reference.com/) was used to compile a dataset of the gamelogs of every game in Steph Curry's career. Then a dataset of the top 100 shooting seasons of all time was compiled, with the criteria:
* 3P% >= 0.400
* 3PA >= 100
* Sorted by TS%
This was to focus on three point shooting in particular, but to have the most efficient shooting seasons of all time represented. It was also to narrow the dataset to focus on shooters, rather than players who are efficient because they play close to the rim. A minimum number of three point attempts was specified to narrow the dataset to consistent three point shooters. Because the MVP is a regular season award, all datasets focussed on the regular season only. 

The Top 100 data is in 'per 100 possessions' form where possible. This is to adjust for pace, because:
> A key tenet for many modern basketball analysts is that basketball is best evaluated at the level of possessions. During a single game, both teams have approximately the same number of possessions, because they alternate possession. (A team can have slightly more if it begins and ends a quarter or half with possession.) However, over the course of the season, teams play at very different paces, which can dramatically color their points scored and points allowed per game. [Source](https://en.wikipedia.org/wiki/APBRmetrics)

Improvements: Steph's MVP season is famed for his three-point shooting, but a more thorough analysis might have done a more extensive treatment of his two-point shooting. Parameters 2P% and 2PA could have been set for the top 100 dataset. 
## Exploratory Data Analysis
The datasets were then imported into Python, cleaned and preprocessed. After previewing the data, exploratory data analysis (EDA) was conducted. This took the form of histograms, boxplot, empirical cumulative distribution function plots (ecdf plots) and quantitative EDA. The features focussed on were 3P%, 3PA, and TS% of the top 100 shooting seasons dataset. In each instance, the data was compared to Steph Curry's 2015-16 MVP season.

Improvements: EDA could have been performed on the Steph Curry career data, to be more thorough. The reason it was not performed is that analysing basketball data by season and analysing players by career statistics is ubiquitous in basketball media, and I was already very familiar with Steph's career stats. EDA might also have been improved by analysing the two-point shooting statistics.
## Hypothesis Testing
The EDA showed that the biggest abnormality in Steph Curry's 2015-16 season compared to the other greatest shooting seasons of all time was his 3PA. Therefore, a hypothesis test was conducted to see if this was an abnormal season compared to his career as a whole. The test statistic was the total number of three point shots made in 79 games (the number he played in 2015-16). The null hypothesis was a hypothesis of exchangeability: 
> Steph's volume of three point shooting in 2015-16 is consistent with his volume across his career.
This was a permutation test using 50,000 permutations.

After 2015-16 season, Curry's team - the Golden State Warriors - signed the basketball superstar Kevin Durant. Since then, they have been virtually unstoppable, winning two championships in a row, but Steph has not won any more MVP awards (despite winning them in back to back years before Durant's arrival). To judge whether Steph has been shooting at the same level since then, a hypothesis test was conducted using the data from the 2015-16 season and the data from 2016-2018. The test statistic was the total number of three point shots made in 79 games. The null hypothesis, again, was a hypothesis of exchangeability:
> Steph's volume of three point shooting in 2015-16 is consistent with his volume since then.
This was a permutation test using 50,000 permutations.

Improvements: The test statistic would have been better chosen as 3PA per 100 possessions, or even 3PA per minute. The number of games played is standardized, but a fairer comparison would have been standardization at a higher level of resolution, perhaps using the minutes played data.
## Hypothesis Testing of Correlation
Steph Curry's three point shooting volume was unique among the greatest shooting seasons of all time, but his three point shooting percentage was merely very good. Was the crazy aspect of the season that he shot so many three-pointers, or that he remained so accurate on such high volume? To gauge the correlation between 3PA and 3P% among the greatest shooting seasons of all time, a hypothesis test was conducted. The test statistic was the Pearson correlation coefficient, and the null hypothesis was: 
> 3P% is not correlated with 3PA among all time great shooting seasons.
This was a permutation test using 50,000 permutations.

Improvements: The dataset might not have been right for gauging the correlation between 3PA and 3P%, as we preselected some of the greatest shooting seasons of all time. A control group with all the nba players playing in 2015-16 might have been useful for comparison.
## Notes
Credit to: 

https://cleaningtheglass.com/

http://dribbleanalytics.blogspot.com/

https://fastbreakdata.com/

https://www.datacamp.com/

https://www.reddit.com/r/nba/

for inspiring my approach to this project.
