---
layout: post
title: NBA Salary Analysis
excerpt: ''
date: 2020-07-07 00:00:00 -0700
last_modified_at: 
categories: []
tags: []
comments: false

---
# Motivation

Discourse around the NBA and its players almost always centers around their talent and performance, as it should. Sometimes factors like coach or teammate quality and general roster construction finds their way into the discussion, and players are rated by the public accordingly, occasionally resulting in labels such as over or underpaid. However, how one player is paid affects others on the team and the salary cap acts as a forcing function on what a team can do, which in turn impacts the roles the players are in on the court. The salary construction of the team and the tools available to the front office are massively important to players' context, and even if tracing through a team's transaction history is often a fool's errand, I think there is room for this data to influence more of the public analysis and understanding. To that end, I went about collecting salary data as far back as possible and attaching it to NBA data.

My initial questions were simply around how height, weight, position, and age influence salary so that I could confirm (or reject) anecdotal assumptions about things such as taller players getting paid more. The elephant in the room is, of course, the NBA's Collective Bargaining Agreement (CBA) and all of its complexities that determine the salary cap and contracts. The CBA is renogiated at the end of each agreement, which typically last between 5 and 7 years (<-- double check), and each new CBA brings its own peculiarities such as the amnesty provision, maximum salary numbers, and changing exception levels. Furthermore, individual player contracts are rarely made completely public and instead rely on media reports for the breakdowns. All of this combines to make it a difficult dataset to both compile and analyze, but I believe it's an important piece of the puzzle.

# Data Collection

## Challenges

The data is around in varying levels of accessibility on websites such as Patricia Bender's website, without which I'm not sure any of this would exist, as well as HoopsHype and (what's the other site??). After struggling to scrape and parse Bender's numbers due primarily to the changing format from year to year, I found HoopsHype's numbers that are more accessible for scraping and compiling into one dataset. The next step in the data wrangling process was connecting it to NBA data. I already had NBA player data after gathering the player pages, box scores, and play by play files a few years ago, and most of the individual player pages include height, weight, position labels (using G / F / C nomenclature), and date of birth.

Unfortunately joining those two data sources was not the easiest, due to differing names, players only showing up in one dataset, and Jaren Jackson and Jaren Jackson Jr. both being in the dataset. I cleaned the names and worked through the rest of the mismatches in the datasets manually, which was a pain, especially after accidentally overwriting my progress twice. The biggest issue was players who were ostensibly brought into training camp and so technically had a contract, but did not get into any games and so did not have a player page on NBA.com. There was some [incorrect birth date data](https://twitter.com/wfordh/status/1353512538286157824) on the league's website and other players had missing heights or weights, so I pulled all of that missing data from RealGM. The finished dataset included 14544 rows of data spanning the 1990-91 season to 2018-19 and included name, team, salary, salary adjusted for inflation, salary as a percentage of the cap, height, weight, position, and age. 

## Analysis

The initial analysis was to create a salary equivalent to the player aging curve to capture the idea of a "prime" in terms of money and more directly address how salary fits into player and team evaluation discussions. While I was successful in creating such a curve for each of the Guard, Forward, and Center positions, the utility of the curves as is not very high yet due to the lack of metadata and the static position labels. 

# Conclusion

# Next Steps

## Direct dataset

		More years

		More metadata, ie type of contract (max, rookie, etc) and CBA signed under

## Other uses

		Connect to RAPM

		Connect to team building