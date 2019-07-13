# Improving BBGM Composite Ratings
Now that we have automatically generated stats from NBA box data, we can generate better composite ratings using real NBA statistics. I built a few linear models (results below) targetting real data  I'll go over some of my proposed changes for the non-defensive [compositeRatings](https://github.com/dumbmatter/gm-games/blob/master/src/basketball/common/constants.js)

## Proposed changes
These are all weighted averages and I'll report the weights scaled so the largest one is 6

### Usage
Add passing. Remove three point, height, dribbling

| Feature | Proposed | Current |
|---------|----------|---------|
|ins         |6.0| 6.0 |
|spd         |2.0| 2.0 |
|pss         |2.0|   |
|fg          |2.0| 4.0 |
|dnk         |2.0| 4.0 |
|oiq         |1.0| 2.0 |
|tp          | | 4.0 |
|hgt         | | 2.0 |
|drb         | | 2.0 |

### Passing
Add speed and inside, remove dribbling

| Feature | Proposed | Current |
|---------|----------|---------|
|pss         |6.0| 6.0 |
|spd         |2.0|   |
|oiq         |2.0| 3.0 |
|ins         |2.0|   |
|drb         | | 2.4 |

### Turnovers
Add height, and lower the effect of passing skill

| Feature | Proposed | Current |
|---------|----------|---------|
|ins         |6.0| 6.0 |
|hgt         |4.0|   |
|pss         |2.0| 6.0 |
|oiq         |-6.0| -6.0 |

### Shooting At the Rim
Adding strength and field goal percentage. Removing jumping and oIQ

| Feature | Proposed | Current |
|---------|----------|---------|
|hgt         |6.0| 6.0 |
|stre        |3.0|   |
|spd         |2.0| 1.6 |
|dnk         |2.0| 3.2 |
|fg          |1.0|   |
|jmp         | | 4.8 |
|oiq         | | 1.6 |

### Low Post Shooting
Just a reweighting

| Feature | Proposed | Current |
|---------|----------|---------|
|hgt         |6.0| 6.0 |
|stre        |3.0| 1.8 |
|spd         |3.0| 0.6 |
|ins         |3.0| 3.0 |
|oiq         |1.0| 0.6 |

### Mid Range Shooting
Our first big overhaul. Ability in dribbling, height, strengh, rebounding should all make you more likely/better at mid-range shooting. Three-point, free-throw, inside and passing abilities should make you less likely to do this.

| Feature | Proposed | Current |
|---------|----------|---------|
|fg          |6.0| 6.0 |
|drb         |4.0|   |
|hgt         |3.0|   |
|stre        |2.0|   |
|spd         |2.0|   |
|reb         |1.0|   |
|tp          |-1.0|   |
|ft          |-1.0|   |
|pss         |-2.0|   |
|ins         |-2.0|   |
|oiq         |-3.0| -3.0 |

### Three Point Shooting
Adding speed and free throw ability.

| Feature | Proposed | Current |
|---------|----------|---------|
|tp          |6.0| 6.0 |
|spd         |1.0|   |
|oiq         |1.0| 0.6 |
|ft          |1.0|   |

### Free Throw Shooting
The regression really wants to bake oiq and speed into this but let's leave it alone

### Rebounding
Add inside, add three point (as a negative), remove jumping, decrease impact of height

| Feature | Proposed | Current |
|---------|----------|---------|
|reb         |6.0| 6.0 |
|hgt         |4.0| 6.0 |
|ins         |2.0|   |
|stre        |1.0| 0.3 |
|oiq         |1.0| 1.5 |
|diq         |1.0| 1.5 |
|tp          |-1.0|   |
|jmp         | | 0.3 |

### Stealing
Add strength. 

| Feature | Proposed | Current |
|---------|----------|---------|
|diq         |6.0| 6.0 |
|spd         |4.0| 3.0 |
|stre        |1.0|   |


### Blocking
This one is mostly fin, but maybe add strength?

| Feature | Proposed | Current |
|---------|----------|---------|
|hgt         |6.0| 6.0 |
|jmp         |3.0| 3.6 |
|stre        |1.0|   |
|diq         |1.0| 1.2 |

### Fouling
Add rebounding!

| Feature | Proposed | Current |
|---------|----------|---------|
|hgt         |6.0| 6.0 |
|diq         |-2.0| -6.0 |
|reb         |-4.0|   |
|spd         |-6.0| -6.0 |

### Drawing Fouls
Adding inside ability, make it less likely that good free throw shooters get fouled. Don't use speed or height. 

| Feature | Proposed | Current |
|---------|----------|---------|
|dnk         |6.0| 6.0 |
|drb         |4.0| 6.0 |
|ins         |3.0|   |
|oiq         |2.0| 6.0 |
|ft          |-3.0|   |
|spd         | | 6.0 |
|hgt         | | 6.0 |


# Regression Results

## All weights

| Usage |  |
|----------|-------|
|ins       |10.0|
|fg        |5.4|
|spd       |4.1|
|pss       |4.1|
|dnk       |2.6|
|oiq       |1.2|
|reb       |-1.0|
|ft        |-1.2|
|diq       |-1.3|
|jmp       |-2.4|
|tp        |-2.8|
|drb       |-4.3|
|stre      |-4.5|

| Passing |  |
|----------|-------|
|pss       |10.0|
|ins       |3.8|
|spd       |2.1|
|fg        |1.7|
|dnk       |1.6|
|ft        |1.5|
|oiq       |1.3|
|stre      |-1.1|
|tp        |-1.2|
|jmp       |-1.9|
|endu      |-1.9|
|reb       |-1.9|
|drb       |-3.8|

| Turnovers |  |
|----------|-------|
|ft        |10.0|
|ins       |8.7|
|endu      |3.4|
|drb       |2.9|
|spd       |2.0|
|stre      |1.0|
|jmp       |-4.0|
|fg        |-11.3|
|oiq       |-13.1|

| Rim |  |
|----------|-------|
|stre      |10.0|
|pss       |3.7|
|hgt       |3.5|
|dnk       |2.6|
|fg        |1.5|
|ft        |-1.7|
|oiq       |-2.1|
|diq       |-3.8|
|spd       |-4.0|
|ins       |-9.6|

| LowPost |  |
|----------|-------|
|stre      |10.0|
|pss       |3.7|
|hgt       |3.5|
|dnk       |2.6|
|fg        |1.5|
|ft        |-1.7|
|oiq       |-2.1|
|diq       |-3.8|
|spd       |-4.0|
|ins       |-9.6|

| MidRange |  |
|----------|-------|
|drb       |10.0|
|fg        |8.7|
|stre      |7.7|
|hgt       |1.7|
|reb       |1.2|
|dnk       |-1.6|
|ft        |-1.9|
|diq       |-2.9|
|tp        |-3.0|
|jmp       |-4.0|
|ins       |-4.6|
|pss       |-4.9|
|oiq       |-5.5|

| 3Point |  |
|----------|-------|
|pss       |10.0|
|spd       |8.0|
|oiq       |7.7|
|tp        |7.4|
|hgt       |1.2|
|reb       |-1.2|
|endu      |-1.3|
|fg        |-2.6|
|jmp       |-3.4|
|stre      |-7.7|
|drb       |-11.2|

| FreeThrow |  |
|----------|-------|
|ft        |10.0|
|oiq       |1.9|
|drb       |1.2|
|tp        |-3.0|
|fg        |-4.7|

| Rebound |  |
|----------|-------|
|reb       |10.0|
|hgt       |5.5|
|fg        |3.8|
|ins       |3.5|
|stre      |1.7|
|diq       |1.5|
|tp        |-1.3|
|drb       |-1.8|
|endu      |-2.3|
|pss       |-2.8|
|ft        |-2.9|
|dnk       |-4.6|

| Steal |  |
|----------|-------|
|diq       |10.0|
|spd       |8.3|
|stre      |7.7|
|ins       |2.4|
|fg        |2.2|
|ft        |1.4|
|drb       |-1.4|
|tp        |-2.6|
|oiq       |-2.8|
|dnk       |-5.4|
|reb       |-7.6|
|jmp       |-8.6|

| Block |  |
|----------|-------|
|hgt       |10.0|
|pss       |9.7|
|stre      |9.4|
|jmp       |7.6|
|tp        |-1.4|
|endu      |-2.6|
|oiq       |-2.9|
|reb       |-4.1|
|ins       |-4.6|
|spd       |-5.6|
|drb       |-6.6|

| Fouling |  |
|----------|-------|
|hgt       |10.0|
|jmp       |5.2|
|pss       |4.4|
|stre      |3.0|
|oiq       |1.8|
|dnk       |-1.6|
|fg        |-2.3|
|tp        |-2.8|
|diq       |-3.4|
|drb       |-4.4|
|reb       |-7.0|
|spd       |-14.3|

| DrawFoul |  |
|----------|-------|
|dnk       |10.0|
|drb       |6.9|
|ins       |5.2|
|endu      |2.5|
|oiq       |1.8|
|reb       |-1.4|
|fg        |-1.7|
|diq       |-5.7|
|ft        |-8.7|



## Positive Weights

| Usage |  |
|----------|-------|
|ins       |10.0|
|spd       |2.7|
|fg        |2.5|
|pss       |2.0|

| Passing |  |
|----------|-------|
|pss       |10.0|
|ins       |1.5|
|dnk       |1.5|
|fg        |1.4|

| Turnovers |  |
|----------|-------|
|ins       |10.0|
|hgt       |6.7|

| Rim |  |
|----------|-------|
|hgt       |10.0|
|spd       |3.7|
|dnk       |3.5|

| LowPost |  |
|----------|-------|
|hgt       |10.0|
|spd       |3.7|
|dnk       |3.5|

| MidRange |  |
|----------|-------|
|fg        |10.0|
|hgt       |6.5|
|spd       |2.3|
|reb       |1.4|

| 3Point |  |
|----------|-------|
|spd       |10.0|
|tp        |8.6|
|ft        |7.3|
|pss       |4.9|

| FreeThrow |  |
|----------|-------|
|ft        |10.0|
|oiq       |5.3|
|spd       |3.9|
|pss       |3.0|
|hgt       |2.2|

| Rebound |  |
|----------|-------|
|reb       |10.0|
|hgt       |7.8|

| Steal |  |
|----------|-------|
|diq       |10.0|
|spd       |4.3|

| Block |  |
|----------|-------|
|hgt       |10.0|
|jmp       |3.6|

| Fouling |  |
|----------|-------|
|hgt       |10.0|
|ins       |1.2|

| DrawFoul |  |
|----------|-------|
|dnk       |10.0|
|ins       |7.0|
|pss       |4.1|
|spd       |1.7|
|hgt       |1.6|
