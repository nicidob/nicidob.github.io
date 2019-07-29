---
title: Automatic Rosters for BasketballGM
---
[BasketballGM](https://basketball-gm.com/) is a pretty awesome game. Some peoeple enjoy playing with real rosters filled with real people. I came up with a way to generate rosters based on box score data. [Write-up](https://nicidob.github.io/automatic_bbgm/) and [code](https://github.com/nicidob/bbgm) are available. This years are all "year ending", so 2019 means 2018-2019 season. These files can be downloaded or just copied and loaded directly from these URLs.

There are NBA, WNBA and NCAA on this site. 

## Current NBA Roster (e.g. as current as possible)
[https://raw.githubusercontent.com/nicidob/bbgm/master/updated_roster.json](https://raw.githubusercontent.com/nicidob/bbgm/master/updated_roster.json)

## NBA with FULL Draft classes
These have draft classes based on rookie performance data until 2019. I picked a few interesting years to generate. These require BBGM v2019.07.21.1313 or newer. 
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1952.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1952.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1967.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1967.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1968.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1968.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1969.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1969.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1977.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1977.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1980.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1980.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1984.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1984.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1992.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_1992.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_2005.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_2005.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/mega_2012.json](https://raw.githubusercontent.com/nicidob/bbgm/master/mega_2012.json)

## NBA
I use two different models here. A "simple" model using box-score data (1952 to 1979), which lacks splits between ORB/ DRB is missing TOV/STL/BLK, etc. The 70s have some of this data but I don't use it. The 1980+ model has all that data.
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1952.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1952.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1953.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1953.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1954.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1954.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1955.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1955.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1956.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1956.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1957.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1957.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1958.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1958.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1959.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1959.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1960.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1960.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1961.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1961.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1962.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1962.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1963.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1963.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1964.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1964.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1965.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1965.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1966.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1966.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1967.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1967.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1968.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1968.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1969.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1969.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1970.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1970.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1971.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1971.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1972.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1972.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1973.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1973.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1974.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1974.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1975.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1975.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1976.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1976.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1977.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1977.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1978.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1978.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1979.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1979.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1980.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1980.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1981.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1981.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1982.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1982.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1983.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1983.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1984.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1984.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1985.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1985.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1986.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1986.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1987.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1987.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1988.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1988.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1989.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1989.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1990.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1990.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1991.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1991.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1992.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1992.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1993.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1993.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1994.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1994.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1995.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1995.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1996.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1996.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1997.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1997.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1998.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1998.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1999.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_1999.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2000.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2000.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2001.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2001.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2002.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2002.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2003.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2003.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2004.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2004.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2005.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2005.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2006.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2006.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2007.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2007.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2008.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2008.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2009.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2009.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2010.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2010.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2011.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2011.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2012.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2012.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2013.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2013.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2014.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2014.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2015.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2015.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2016.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2016.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2017.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2017.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2018.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2018.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2019.json](https://raw.githubusercontent.com/nicidob/bbgm/master/rosters/auto_roster_2019.json)

## NBA All-Time-Great Era Teams
In this version, with 2019 teams, each roster has the 10 highest rated players who played for that team. The year is "best player since that year". So the 2010 roster only has players since 2010. 
[https://raw.githubusercontent.com/nicidob/bbgm/master/era_1960.json](https://raw.githubusercontent.com/nicidob/bbgm/master/era_1960.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/era_1980.json](https://raw.githubusercontent.com/nicidob/bbgm/master/era_1980.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/era_1990.json](https://raw.githubusercontent.com/nicidob/bbgm/master/era_1990.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/era_2000.json](https://raw.githubusercontent.com/nicidob/bbgm/master/era_2000.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/era_2010.json](https://raw.githubusercontent.com/nicidob/bbgm/master/era_2010.json)

## WNBA
WNBA is hard because the distributions don't match that well, but the 2019 season is available here
[https://raw.githubusercontent.com/nicidob/bbgm/master/wnba_roster_2019.json](https://raw.githubusercontent.com/nicidob/bbgm/master/wnba_roster_2019.json)

## NCAA Basketball
This is a giant file with all D1 Teams. But has logos, divisions, etc. [https://raw.githubusercontent.com/nicidob/bbgm/master/cbb_roster_2019.json](https://raw.githubusercontent.com/nicidob/bbgm/master/cbb_roster_2019.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/cbb_roster_2018.json](https://raw.githubusercontent.com/nicidob/bbgm/master/cbb_roster_2019.json)

## Notes
### Statistics
I use statistics from simulated BBGM seasons, then calibrated the data to have a half dozen guys in the 70s (7 in my 2018-2019 rosters ATM).

In 250 auto-played seasons, I had 1500 player-year examples in the 70s (usually 6 guys). 85 examples in the 80s (one in every 3 years), and 7 examples in the 90s (3 times a century). 360, 18 and 2 players hit those marks (70, 80, 90). Using those numbers in the NBA dataset, we'd expect 90 guys who broke 70, 5 guys who broke 80, and 0.5 guys who broke 90. In all of my rosters, using players at their peaks, I have 103 who broke 70, 5 guys who broke 80, 0 guys who broke 90.

Basically.. they're pretty much in line with what BBGM generates.

Now there is a quirk... [BBGM has more aggressive development curves than the real NBA](https://i.imgur.com/3VqBaa3.png). In the NBA, while there is growth, a 19/20 year old rookie (mitchell, luka) can put up 20/5/5, even when their scoring will peak below 30 points a game. In BBGM, there's aggressive development until age 27. I set draft classes based on rookie year performance. But I guess if you have a 20 year old scoring 20pts/game in BBGM, the development model might drive them to be an 80+ player way more often than in real life.

But to fix that last bit, I probably want a more wholistic rookie model that uses their career data, not just their rookie year data. And then somehow deconstructs the BBGM development data. But that'd lead to a lot of... MJ being a complete bust type of situation way too often.

### Era adjustment
Players are all rated compared to league average in that season. And in some ways ... forecasted to BBGM/2019 basketball. So there's 3 point gods even in eras without much (or any) 3pters. All the rosters before 1980 also use a much simpler model (only using Total Rebounds, no Turnover, no steals, no 3pt data, etc.) so those ratings are more off at times.

