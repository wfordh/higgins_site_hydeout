---
layout: post
title: 'Reproducing MLB Showdown '
excerpt: Capturing nostalgia and satisfying curiosities with the help of a bot
date: 2021-01-31 00:00:00 -0800
last_modified_at: 
categories: []
tags: []
comments: false

---
My brother and I played [MLB Showdown](https://showdowncards.com/) a lot growing up, contributing to my interest in the intersection of sports and numbers. We actively played it even after Wizards of the Coast discontinued it after only six years and went so far as producing our own set of cards one year. Unfortunately, it is pretty time intensive to create a full set of cards and it's hard to know if you did a good job, however that's defined. I made an effort to test how faithful cards would be to real baseball with a basic simulation a couple years ago (oof that code), but struggled to figure out assigning on base / out combinations for hitters. I endeavored to do this so I could make historical Showdown cards for players who had an anomalously good season, were Hall of Famers or Hall of Very Good-ers, or were notable for some other reason. These player seasons have always been out of reach and after the holidays I decided to try translating arbitrary seasons to Showdown's context yet again.

I sent out a [tweet](https://twitter.com/wfordh/status/1348024550617878530) to [Chris Long](https://twitter.com/octonion), a polymath and polyglot who knows a ton about sports analytics, different computer languages, and other general knowledge, and often shares little tidbits on Twitter. While he did not respond himself, I did receive a reply from someone who built exactly the tool I was looking for - [showdown bot](https://www.showdownbot.com/). It basically takes a player name and season combination, pick the Showdown "context" you want, and it outputs a player card. My brother and I have created hundreds of cards with it and the generated cards have been pretty reasonable, though it is fun to stress test it and finding the edge cases is fun.

I looked for these oddities with help from Fangraphs' search functionality, picking down seasons from superstars, scrolling through award seasons on Baseball-Reference, and using its player comparison tool. Some of the best include Lefty Grove having an IP 6 reliever season - where he also won over 20 games! Brendan McKay's 2018 season results in an IP 4 starter. Adalberto Mondesi's 2018 card gets a single plus at 10 and Byron Buxton's 2020 season is on base 9 and 1-9 out, but then has 13+ homer! Both of these cards shed some light on perhaps the greatest oddities of the bot because of how it tries to match the player's actual line with their showdown line - small sample size players. Everyone agrees that Ke'Bryan Hayes started his career off with a smashing success in 2020, and it results in a 730 point beast of a card despite having only 95 plate appearances. This is one of my favorite parts of the tool, and it doesn't detract from the total experience because the points for these players make sense given their cards. It also serves as a reminder that even the almighty algorithm can serve up some funky results when given odd data and those results should be scrutinized and contextualized accordingly.

![2020 season in 2005 context](assets/img/screen-shot-2021-01-31-at-3-26-10-pm.png "Byron Buxton")

The context is important to anyone who played the original Showdown because they know it had players who were obviously over or under priced, effectively limiting the player pool even more. Though it was hilarious to see players who should seemingly be 100 points more or less, in the end it took options away from the game. This algorithm avoids that issue and stays consistent, making team building simultaneously more interesting and more difficult by exploding the usable number of cards. Part of me wishes there was still some of this randomness in the point totals, but it's a net positive to not have such unexplained inconsistencies.

It's a really neat project from both a practical and technical standpoint, though unfortunately there's no way for the user to either create multiple cards at once or save the card. This limits the usability of these cards and, though I've talked with Matt Gula, the creator, a little bit over Twitter, I'm not sure if making a functional game is in the scope of the project. I do have some questions about the implementation - why query Baseball Reference for each card generation instead of using something like the Lahman database? - but all of the Python code is [available on GitHub](https://github.com/mgula57/mlb_showdown_card_bot). I wrote a [script](https://github.com/wfordh/mlb_showdown/blob/master/showdown_bot_tools/run_showdown_bot.py) for creating and saving multiple cards at once, which only requires a text file with comma separated player / season combinations to pull the cards using showdown bot before saving them locally. There are minor improvements I want to make such as connecting the cards to Google Drive and checking to see if the card has already been made, but it was a simple solution that gets 80% to solving the issue.

The next step of turning it into a functional game is a much larger project though, and would require both more time and better coding skill than I probably have. Until that happens, we'll make do with the cards we have and continue searching for the most unusual cards, learning random baseball facts along the way. After all, Showdown bot has taken out the hardest parts of playing games with any card ever. I'm looking forward to searching for the right cards to build a team capable of crushing my brother's, which is what this is all about.

regularization in bayesian methods??

homology to detect holes in a defense?

drafts as multi-armed bandit?

keep or cut app??

***

Reading:

\- shreya shankar predictive modeling

\- fs blog mistrust

\- notes on camp

\- ndsp pdweb

Next:

\- salaries writeup

\- BMH ch 7

\- ottoneu tool - gmail part and getting stats

\- sports & goodhart's law

\- once done with BMH, then unit testing?