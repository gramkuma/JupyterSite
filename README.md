# Sabermetrics Final Project

### Contents
- baseballdatabank-master : Contains data used by the jupyter notebook
- Explanation of Statistic: A writeup of the statistic invented.
- Final Project.ipynb : Ipython notebook containing the analysis.
- index.html : Generated html for Github pages website
- YouTube Video : https://youtu.be/WFgZeHr3P8A


### Explanation of the Statistic

#### The Problem	

While we have a plethora of ways to evaluate how good a batter or a pitcher is, fielding is often overlooked. The way a team fields the ball is most of the defense a team has. The current way we calculate fielding percentage is pretty naive. I think that simply using the regular formula (Putouts + Assists) / (Putouts + Assists + Errors) doesn’t give proper credit to the fielder for participating in a double play (performing in a high pressure situation) or punish the player for wild pitches, or passed balls. Moreover, the definition of an error is subjective since that call is made by the official scorer. The old definition of fielding percentage also doesn’t take into account the fielders position and how many balls they field at their position compared to the league average. If you get to less balls in the field, the less errors you can make. Rather than punishing a player for making a lot of plays and subsequently accruing more errors than a less motivated player, I wanted to include the ratio of good to bad plays they made into the fielding percentage calculation.

#### The Solution

The new statistic that I propose is Range Adjusted Fielding Percentage. The first step I took to building the statistic was to include the statistics that I thought would add accuracy to fielding percentage, so I added the number of double plays, passed balls and wild pitches to the formula for fielding percentage. This adds a little extra insight to a fielder’s performance in high stake situations (double plays) but for the most part it just punishes pitchers and catchers for committing errors and allowing the batting team a slight advantage. The next step, was to include the variability of range in the formula. In order to do this, I calculated my version of fielding percentage for each position ( catcher, 1B, 2B, 3B, outfield, pitcher and shortstop) as well as the league average fielding percentage. I created a statistic called expected range factor which is just the league average minus the average fielding percentage at each position squared.  I then calculate the range factor for a player by dividing the players based on which position they play, calculating their fielding percentage and subtracting that from the league average. This allows me to have the expected range factor act as a benchmark for each players range factor. I can then compare the two to see how a player’s fielding chalks up to the average for his position. To finish the statistic I arbitrarily weight the comparison and multiply that with my version of the fielding percentage to influence the player’s final score with his performance.
  
  
This statistic is closely related to UZR, Fielding Percentage and it also uses a modified version of Bill James’s range factor. While UZR tries to assign a run value to a defensive player, my statistic only considers how the player handles the balls he picks up without taking into other situational factors. I would say that my statistic, since it is based off of fielding percentage, is closely related to fielding percentage as well. My statistic, while not as simple as Fielding Percentage, does try to account for the range of a defensive player at their position. I believe that my statistic does get comparable yearly values since it compares each player to the average performance in their position in a season. Using the performance stat that I calculate (expected range factor - player range factor) you can tell if a player has had a constant defensive showing that season or not.
