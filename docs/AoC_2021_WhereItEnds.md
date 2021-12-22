---
layout: default
title: "2021 - The Days of Our Lives"
permalink: /2021/d21/
date: 2021-12-21 13:00:00 -0000
categories: AdventOfCode AoC 2021
---
# [--- Day 21: Dirac Dice ---](https://adventofcode.com/2021/day/21)
## or..
## If you roll the dice enough they become sand...
![one art please](/docs/assets/img/rollthebones.png)
# Part 1

## [Python](https://github.com/aaronlael/AoC-2021/blob/master/AoC_2021_D21P1.py)

So simple you knew you were about to get your butt absolutely handed to you by part 2.  

## [Go](https://github.com/aaronlael/AoC-2021-Go/)

Still catching up

# Part 2

## [Python](https://github.com/aaronlael/AoC-2021/blob/master/AoC_2021_D21P2.py)

Lanternfish?  Polymers?  Yes, this is a problem for caching once more.  I just had a very hard time getting the concept of what to cache to make my code "performant."  I found a hint in a help thread on reddit that basically pointed towards tracking the state of games, since those were not unique.  To do this, I re-rewrote my game state dicts as strings so they could be dict keys:

```Python
# converts dict to game state string
def gamestate(game) -> str:
    # player1|position p1|score p1| player2 | position p2 | score p2
    return f"""1|{game["1"]["pos"]}|{game["1"]["score"]}|2|{game["2"]["pos"]}|{game["2"]["score"]}"""

# converts the game state string back into the original dict for easier parsing
def unformat(gamestate) -> dict:
    g = gamestate.split("|")
    d = { "1" : {"pos" : int(g[1]),
                    "score" : int(g[2]),
                    },
            "2" : { "pos" : int(g[4]),
                    "score" : int(g[5]),
                    }
            }
    return d
```
Once I had this in place, I had a solution that completed in 40 seconds which is fast enough for me.

## [Go](https://github.com/aaronlael/AoC-2021-Go/)

We'll see.

[<<](AoC_2021_D20.md) - [Table of Contents](AoC_2021.md) - [>>](AoC_2021_D22.md)
