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

Unfortunately joining those two data sources was not the easiest, due to differing names, players only showing up in one dataset, and Jaren Jackson and Jaren Jackson Jr. both being in the dataset. I cleaned the names and worked through the rest of the mismatches in the datasets manually, which was a pain, especially after accidentally overwriting my progress twice. The biggest issue was players who were ostensibly brought into training camp and so technically had a contract, but did not get into any games and so did not have a player page on NBA.com. There was some [incorrect birth date data](https://twitter.com/wfordh/status/1353512538286157824) on the league's website and other players had missing heights or weights, so I pulled all of that missing data from RealGM. The finished data set included 14544 rows of data spanning the 1990-91 season to 2018-19 and included name, team, salary, salary adjusted for inflation, salary as a percentage of the cap, height, weight, position, and age. 

## Analysis

The initial analysis was to create a salary equivalent to the player aging curve to capture the idea of a "prime" in terms of money and more directly address how salary fits into player and team evaluation discussions. While I was successful in creating such a curve for each of the Guard, Forward, and Center positions, the utility of the curves as is not very high yet due to the lack of metadata and the static position labels. Each position begins just above 0 at about 2% of the cap and reaches a peak value around age 29 of around 10% of the salary cap before tapering off as the player ages to final values slightly higher than the beginning of their career. 

If you have knowledge of the CBA, then none of this should be surprising. Players enter the league and are restricted to rookie contracts before they are able to sign contracts with a variety of structures during their prime. For older players the dispersion of salary is apparent as some reap the benefit of stardom with contracts worth 25-35% of the cap while others stay just above 0 with the veterans' minimum and others are not included in the data set at all as they are unable to remain in the league. Knowing this and looking closer at the endpoints of the player age distribution makes it clear the large impact selection bias has on the data where it begins at around 18 years old and ends past 40 for each position. However, players are only in the league at these extreme ages if they are very good. If someone is 18 and in the league, then they were likely a first round pick and thus will command a salary above the minimum. Many other players enter the league between 22 and 24 years of age and are not all first round picks, so there will be many more data points at the minimum to drag the curve down. On the other hand, older players will only stick in the league if they are good enough or are named Udonis Haslem, and the league minimum increases with years in the league while the amount it counts against the salary cap stays constant after 3 years in the league **(<-- check that)** and we are using the actual salary and not what it counts against the cap in this data.

In addition to player age, I wanted to compare average salaries to player height, weight, and BMI for each position. Average salary is a bit crude and might misrepresent some players if they had a particularly spiky salary curve, but it's a good first pass at the data. Only height has any sort of relationship with salary, though that's consistent across all positions, and weight and BMI are more or less flat with small peaks towards the middle of the ranges.

# Conclusion

The salary cap is a crucial part of the NBA, but one that remains a bit mysterious due to its built up rules from years of patching up whatever issues pop up during the course of the last CBA. It also falls through the cracks of most statistical analyses as they tend to  focus on the on-court product or evaluating roster decisions from events such as the trade deadline or the draft. Though this project was a bit laborious with the data acquisition and cleaning, it was rewarding. The data set will add another set of dimensions to cut analyses by and I think there is more juice to squeeze from the data as more metadata is added. 

The age curves are not quite as useful as I hoped, they line up with expectations and the supplementary curves for height, weight, and BMI are also useful. They are some of the first things we learn about players - well, not BMI - and it's good to see how they might inform players' salaries. 

# Next Steps

## Direct dataset

		More years

		More metadata, ie type of contract (max, rookie, etc) and CBA signed under

Years in league instead of age

## Other uses

		Connect to RAPM

		Connect to team building