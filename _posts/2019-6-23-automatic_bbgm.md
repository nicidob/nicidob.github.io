---
layout: post
title: Automatically Generating NBA Rosters for BasketballGM
---
[BasketballGM](https://basketball-gm.com/) is a remarkable, free, browser-based game. I decided to automatically generate roster files from real NBA data using some basic data science methods. The results are all on [this GitHub repo](https://github.com/nicidob/bbgm) and the roster files are [available here](https://github.com/nicidob/bbgm/releases)


## BasketballGM Ratings
As outlined on [the player customization page](https://basketball-gm.com/manual/customization/players/), players in BBGM have 15 ratings which determine their performance. 
* **hgt**: height, which factors into pretty much everything 
* **stre**: strength, which influences defense, rebounding, and low post scoring
* **spd**: speed, which influences ball handling, fast breaking, and defense
* **jmp**: jumping, which influences finishing at the rim, rebounding, blocking shots, and defense
* **endu**: endurance, which governs how fast a player's skills degrade as he gets tired
* **ins**: low post scoring
* **dnk**: dunking/layups
* **ft**: free throw shooting
* **fg**: 2 point jump shot ability
* **tp**: 3 point shooting
* **oiq**: offensive IQ 
* **diq**: defensive IQ
* **drb**: dribbling
* **pss**: passing
* **reb**: rebounding

This is a sensible decomposition of latent performance variables. Unfortunately, it's not totally clear how to set these manually. For example, take 3Pt shooting. Shooting percentage? Domantas Sabonis shot over 50% on 3P (on 17 attempts). Total makes? Harden made 378 3P but Steph Curry made 354, with 200 less 3PA. Even worse are variables like **jmp** or **drb**, which I have no idea how to set correctly for large numbers of players. 

So instead, we'll build a model to understand these underlying variables. 

# Building a model
What type of model? In general, we want **a model that takes data we have, and generates data we want**. It's clear we want the underlying variables. As for what data do we have? Box score statistics, like [this page](https://www.basketball-reference.com/players/j/jamesle01.html) for LeBron James. This is your typical stat sheet, Rebounds, Points, Steals, etc. Since we're using modern NBA data, we also have per possession and per minute versions of these statistics. 

Our basic model will be a linear regression, which is just a weighted sum. For example, we might get that a player's jump score can be derived as *Jump = 0.3 * Blk_p36 - 0.4 * Height - 0.4 * Age + 0.2 * MP*. Stated in plain words, this means that a player who is young, plays a lot of minutes, and gets a lot of blocks would tend to have a high jump rating. We'll [whiten the data](https://en.wikipedia.org/wiki/Whitening_transformation) first, so all of these are in consistent units, which are standard devations above/below the mean. 

This idea is hardly new. This is [Box Plus Minus](https://www.basketball-reference.com/about/bpm.html) basically works, it's a model from box score data to something like [Ridge-Regressed APM](http://www.sloansportsconference.com/wp-content/uploads/2015/09/joeSillSloanSportsPaperWithLogo.pdf). There are many versions of this, such as those from [Dan Rosenbaum](http://www.82games.com/comm30.htm) and [Scott](http://basketball-statistics.com/seredayanalysispartone.html) [Sereday](http://basketball-statistics.com/seredayanalysisparttwo.html). Further, [Ben Taylor](http://www.backpicks.com/) has built models to measure [Shot Creation](https://fansided.com/2017/08/11/nylon-calculus-measuring-creation-box-score/), [Passer Rating](http://www.backpicks.com/2018/07/15/nba-passer-ratings-since-1978/) and [Offensive Load](http://www.backpicks.com/2017/10/16/offensive-load-and-adjusted-tov/). 

### Getting NBA data
I decided to use the wonderful [Basketball Reference](https://www.basketball-reference.com) as a data source. I have a small script (`save_season.py`) which downloads the team-by-team pages for a given season, along with the contract files (which are always "as of today" and don't provide historical data). I extract all the tables from the pages and save them into Python pickle objects. 

### Getting BBGM data
This step is really easy, grab some simulated BasketballGM seasons, and export the league statistics. I used data from a league I'd been playing with (~11,000 players). This exports box score data in per game averages, along with a few advanced stats. Now we have a dataset of BBGM data where we know both the underlying player ratings, and what box score data they generated. 

One huge benefit is that this captures all the simulation quirks of BBGM, such as the significant impact that **height** has a player's performance. If BBGM changes how it does simulation, we can simply autoplay a few dozen seasons and build a new model. 

With this, we fit a standard regularized linear regression model for all the underlying variables. 

# Results
Now that we have a model and a way to obtain NBA box score data, we can build a roster automatically. And we can do it for any year, thereby also obtaining old draft classes (just use the rookie year data). For the current season, we can also automatically setup all the player contracts. Since it's automatic, we can just as easily build rosters for 1985, 1992, 2010 or 2012 as we can for 2019. Except 2019 lacks accurate draft classes (I don't currently use college data, although one could), and all other years lack player contract data.

There are a few caveats
1) This is just a statistical regression; it's a linear model and it's far from perfect.
2) This is just based on box score data; it doesn't factor in teammate performance, injuries or coasting during the regular season.
3) This may produce slightly different models every time I run it, and depending on input features
4) Many of these features are per minute adjusted and sometimes a player with an amazing few minutes acquires amazing statistics (see [Trevon Duval's](https://www.basketball-reference.com/players/d/duvaltr01.html) Advanced & Per36 numbers in 2018-2019)

For the 2018-2019 season, my current configuration produced the top players as James Harden (ovr:75), Kevin Durant (ovr:68), Paul George (ovr:68). The highest potential players are Luka Doncic (ovr: 62, pot:82), Jarret Allen (ovr: 61, pot: 75), and the aforementioned James Harden. The Top 10 teams were GSW, UTA, BOS, MIL, PHI, DEN, WAS, HOU, TOR, BKN (no injuries). 

## Comparing the results against standard rosters
[Alexnoob's rosters](https://github.com/alexnoob/BasketBall-GM-Rosters) are the best curated set in the BBGM community. We can compare his rosters against the automatic ones. X axis is a score alexnoob gave someone. Y axis is the automatic score. The plots are ordered/colored by how well they correlate with each other. This highlights where it's easy to score players (overall, rebounding, 3p%) and where it's hard (jmp, diq). 

<p align="center">
  <img src="/images/p1.png">
</p>
<p align="center">
  <img src="/images/p2.png">
</p>

## Analyzing the model
So let's take a look at what the model uses to produce the 15 ratings for BasketBallGM. As is well known, height highly impacts a player's performance in BBGM. If you include it as an input feature, almost all scores will have a negative value for height. Why? Because extra height helps box score stats so all the other variables have to subtract a bonus for height first. For this analysis, ([Release 0.2](https://github.com/nicidob/bbgm/releases/tag/0.2) on GitHub), the input features were 'FG%', '3P%', 'FT%', 'AtRimFGP', 'LowPostFGP', 'MidRangeFGP', 'TS%','3PAr', 'FTr', 'ORB%', 'DRB%', 'TRB%', 'AST%', 'STL%', 'BLK%', 'TOV%', 'USG%', '+/-', 'MP', 'FGp36', 'FGAp36', '3Pp36', '3PAp36', 'FTp36','FTAp36', 'ORBp36', 'DRBp36', 'TRBp36', 'ASTp36', 'TOVp36', 'STLp36','Blkp36', 'PFp36', 'PTSp36', 'OWSp36', 'DWSp36', 'Creation', 'Load', 'cTOV', 'Age'. Some sensitivity analysis would be great here but I haven't done that yet. Remarkably, although I perform standard scaling before passing real data through the model, the unscaled NBA data looks very similiar to BBGM data. Well done [Jeremy](http://dumbmatter.com/)!
<p align="center">
  <img src="/images/p3.png">
</p>

Now we'll analyze the 5 largest coefficients to see how the latent variables in BBGM get expressed in performance. 

### Height

| Variable | Coeff |
|----------|-------|
|PFp36                    |0.38|
|BLK%                     |0.23|
|Blkp36                   |0.21|
|DWSp36                   |0.13|
|ORB%                     |0.12|

The most important variable in BBGM. Predicted by fouls, blocks and rebounding. If fouls predict height, then our other variables will use fouling a surrogate for height, and try to remove the effect of height. Expect a lot of negative PFp36, BLK% and Blkp36 for the other statistics. 

### Strength

| Variable | Coeff |
|----------|-------|
|MP                       |0.24|
|USG%                     |0.15|
|+/-                      |0.13|
|ASTp36                   |-0.17|
|PFp36                    |-0.20|

Strong players play more minutes, with higher usage, low assist numbers

### Speed

| Variable | Coeff |
|----------|-------|
|Blkp36                   |0.21|
|BLK%                     |0.20|
|MP                       |0.17|
|Age                      |-0.28|
|PFp36                    |-0.47|

Speedy players play a lot of minutes and aren't very old.

### Jumping

| Variable | Coeff |
|----------|-------|
|Blkp36                   |0.29|
|BLK%                     |0.28|
|MP                       |0.17|
|PFp36                    |-0.39|
|Age                      |-0.45|

Players with good vertical are young and block well. 

### Endurance

| Variable | Coeff |
|----------|-------|
|MP                       |0.40|
|Blkp36 Age               |0.18|
|BLK% Age                 |0.17|
|MP 3Pp36                 |0.11|
|PFp36 Age                |-0.16|

Players with high endurance play a lot of minutes.

### Inside

| Variable | Coeff |
|----------|-------|
|USG%                     |0.25|
|TOVp36                   |0.23|
|FGAp36                   |0.20|
|FGp36                    |0.17|
|cTOV                     |0.16|

### Dunking

| Variable | Coeff |
|----------|-------|
|Age                      |0.24|
|FTAp36                   |0.24|
|FTp36                    |0.22|
|AST%                     |-0.20|
|ASTp36                   |-0.21|

Shooting a lot of free throws and not passing is indicative of being a dunker. 

### Free Throws

| Variable | Coeff |
|----------|-------|
|FT%                      |0.61|
|FT% MP                   |0.24|
|FTAp36                   |-0.14|
|FG%                      |-0.15|
|FTr                      |-0.17|

Free throw shooting is predicted by shooting a lot of free throws and playing a lot of minutes. 

### Two Pointers

| Variable | Coeff |
|----------|-------|
|MidRangeFGP              |0.33|
|FT%                      |0.21|
|TS%                      |-0.19|
|FTr                      |-0.21|
|FG%                      |-0.27|

Shooting 2 pointers is predicted by midrange FG% and FT%. 

### Three Pointers

| Variable | Coeff |
|----------|-------|
|3PAr                     |0.40|
|3PAp36                   |0.26|
|3Pp36                    |0.21|
|FG%                      |-0.09|
|FTr                      |-0.10|

Shooting 3 pointers is predicted what fraction of your shots are from 3, along with 3P and 3PA. 


### Offensive IQ

| Variable | Coeff |
|----------|-------|
|OWSp36                   |0.22|
|MP                       |0.21|
|MidRangeFGP              |-0.17|
|BLK%                     |-0.18|
|Blkp36                   |-0.19|

Offensive Win Shares per 36 minutes and minutes played suggest a smart offensive player. 

### Defensive IQ

| Variable | Coeff |
|----------|-------|
|STLp36                   |0.32|
|STL%                     |0.31|
|Age                      |0.25|
|TRB%                     |0.16|
|ORB%                     |0.15|

Older players with good rebounding and a high number of steals are smart defensive players. 

### Dribbling

| Variable | Coeff |
|----------|-------|
|ASTp36                   |0.28|
|Creation                 |0.23|
|AST%                     |0.20|
|PFp36                    |-0.15|
|DWSp36                   |-0.17|

Players who dribble well tend to pass well and create shots for others. 

### Passing

| Variable | Coeff |
|----------|-------|
|ASTp36                   |0.32|
|Creation                 |0.26|
|AST%                     |0.22|
|PFp36                    |-0.17|
|DWSp36                   |-0.19|

Passing looks like dribbling. 

### Rebounding

| Variable | Coeff |
|----------|-------|
|ORBp36                   |0.28|
|ORB%                     |0.25|
|TRB%                     |0.24|
|DRB%                     |0.23|
|PFp36                    |-0.27|

Rebounders tend to have good rebounding rates.

## Compared to AlexNoob
For 2019, the following players had large drops in overall rating compared to Alexnoob's roster: Avery Bradley (-15), Russell Westbrook (-15), Austin Rivers (-13), OG Annuboy (-13), Kevin Knox (-12), Brandon Ingram (-8). Small usage players like Ekpe Udoh got a large boost (+16). Of players with significant minutes, Trae Young, Miles Plumlee, Timofey Mozgov, Michael Carter-Williams all got boosts of +4. 

## Normalizing Rosters
If you don't trust the automatic rosters, and really love [Alexnoob's](https://github.com/alexnoob/BasketBall-GM-Rosters) rosters, urge you to consider using normalized rosters. Normalization here just means -- shift the distribution of ratings so they match the natural distribution of ratings. You can see what the before (left, orange) and after (right, green) distributions look like for the 15 ratings, compare to the blue data from randomly generated BBGM seasons. I also include normalized rosters on my GitHub releases page, and the notebook `correct_base.ipynb` performs the correction. 
<p align="center">
  <img src="/images/plot.png">
</p>
Since this is just a scale and shift for each rating, the changes are monotonic. If AlexNoob gave someone a higher rebounding score than someone else, they'll still have a higher score in this corrected version. However, since this is done independently by category, it may change the overall scores. The automatically generated players from future seasons should also blendly smoothly with existing rosters, as they have similiar distributions. 
