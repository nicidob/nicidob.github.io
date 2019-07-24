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

## WNBA
WNBA is hard because the distributions don't match that well, but the 2019 season is available here
[https://raw.githubusercontent.com/nicidob/bbgm/master/wnba_roster_2019.json](https://raw.githubusercontent.com/nicidob/bbgm/master/wnba_roster_2019.json)

## NCAA Basketball
This is a giant file with all D1 Teams. But has logos, divisions, etc. [https://raw.githubusercontent.com/nicidob/bbgm/master/cbb_roster_2019.json](https://raw.githubusercontent.com/nicidob/bbgm/master/cbb_roster_2019.json)
[https://raw.githubusercontent.com/nicidob/bbgm/master/cbb_roster_2018.json](https://raw.githubusercontent.com/nicidob/bbgm/master/cbb_roster_2019.json)