# Fantasy Football Recommendations Using Machine Learning

![Summary Figure](/images/Fantasy_Football_ML_summary_figure.jpg)
[GitHub README - https://github.com/CS4641-2021/sports-numbers-fans#readme](https://github.com/CS4641-2021/sports-numbers-fans#readme)
## Introduction

The goal of this project is to accurately predict average fantasy football performance for NFL wide receivers throughout a single season. Performance is calculated via points that can be earned by a player for accumulating yards gained, touchdowns scored, or passes caught. Similarly, points can be lost by a player for losing yards or fumbling the ball. At the end of every game, a player's total points are tallied, and the player with the highest number of points has the most value for that game.

Players of *fantasy* football, users, will select a roster of players every week in an attempt to accumulate the highest sum of points via their roster. Users will use a variety of information to make an informed decision on their roster selection. Typical facets of information include previous player performance, player matchups, scouting reports, and projected points. From personal experience, most players tend to lean towards projected points as the main indicator for their analysis.


## Methods

We aggregated data from fantasydata.com for the 2017-2020 season. Our data consists of approximately 35 features which reference a receivers performance in a given year. Since we are trying to predict 2020 results given 2019 data, we have three complete seasons of data to work with with approximately 75 data points per season. 

We visualized and clustered our data using a couple unsupervised machine learning techniques in order to understand our data. We created a coorelational heat map to understand relationships in features. We used K-means clustering in order to identify any potential groupings in our data points. Additionally, we used parallel coordinates to visualize a normalized version of our data, which was grouped into bins according to the target variable. All of these methods together gives us an understanding of where potential sources of error can occur for a regression model.

We tested multiple regression models, and given our relatively low number of data points and high features, we decided to use Bayesian ridge regression with a normalized feature set.

## Results

![Bayesian Ridge](/images/Bayesian Ridge Regression Test Results.png)
<img src="/images/Bayesian Ridge Regression Test Results.png">

For results, we are looking to develop an accurate predictive model to rank the best wide receiver in a fantasy league line-up. This predictive model would give the  best recommendation for a wide receiver with the highest projected points in the league game-to-game matchup. We plan to extend the learning model to other player positions, as time permits. This model would enable individual end-users to make informed decisions on player selection for maximum "fantasy" points.

## Discussion

Player performance is typically calculated through sentiment analysis and season simulation adjusted for defensive pairings<sup>1</sup>. However, we will be taking a different approach to our player performance projections in order to eliminate the sentiment factor which could contribute bias to the model. We will be strictly using a player's matchup and statistics such as height, strength, speed, and prior performance. In addition, we will attempt to group similar style players and defenses together to help aid in our predictive model. 

## References
<sup>1</sup>Greenberg, Neil "How The Post’s fantasy football projections work". The Washington Post
https://www.washingtonpost.com/sports/2019/08/14/how-posts-fantasy-football-projections-work/

<sup>2</sup>Fantasy Data, https://fantasydata.com/nfl/fantasy-football-leaders?position=4&season=2020&seasontype=1&scope=2&subscope=1&startweek=1&endweek=1&aggregatescope=1&range=3

<sup>3</sup>Sports Data, https://sportsdata.io/developers/data-dictionary/nfl

<sup>4</sup>NFL Statistics, https://www.kaggle.com/kendallgillies/nflstatistics?select=Career_Stats_Receiving.csv
