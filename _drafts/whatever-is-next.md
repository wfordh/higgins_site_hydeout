---
layout: post
title: What Comes Next?
excerpt: Upcoming job hunt, personal projects, and D&D characters
date: 
last_modified_at: 
categories: []
tags: []
comments: false

---
Last week I was [laid off](https://twitter.com/wfordh/status/1329887120148852744) from [Scoop](https://www.linkedin.com/feed/update/urn:li:activity:6737089974644158464/). It sucks that our country has handled the pandemic so poorly that many things are not even close to normal. The state of things certainly impacted Scoop, especially as a transportation company, and of course impacted me. I really enjoyed my time at Scoop and in particular my analytics teammates. We were a model team and the camaraderie we had is not something I'll forget soon. In fact, it might make my next job that much tougher because it will be measured against such a high standard. Anyway, enough of that as everyone has their own horror stories from 2020.

***

I have worked on a couple different [fantasy football tools](https://twitter.com/wfordh/status/1331394026357010433) to help me in addition to reading FantasyPros and The Athletic articles. I was able to get both of them off the ground before the season ended, which is pretty exciting considering I've had an awkward habit of not finishing these sorts of things until after the season. They are both command line Python scripts that take a couple of arguments and then print out some JSON blobs of information to the terminal. Neither one is very complicated and they mainly leverage the [Sleeper API](https://docs.sleeper.app/) to get the league information. It's really helpful that Sleeper has all of that data available, and there's even a [Python wrapper](https://pypi.org/project/sleeper-api-wrapper/) to the API, though it looks like it hasn't been updated in a while.

The first one pulls all of the user's scores from the previous weeks and calculates and "expected" record / win percentage based on how many teams each team would have beaten that week. It's a simple way to keep the context of the weekly scores and seasonality of the NFL, but make the records independent of the weekly matchups. On top of that, it provides a rest of season strength of schedule for each team by averaging their remaining opponents' expected win percentage.

The second one is meant to help with waivers and finding players to add/drop. Unfortunately, Sleeper has restricted access to their stats projections at the behest of their stats provider, so I'm currently pulling in Numberfire's projections. The script pulls in all of the free agents and rostered players in our league, adds the projections, and then compares the free agents to the players on my roster to see which players have better rest of season projections than those on my roster.

There are some additions I'd like to make to each script to make them more comprehensive, but now that the first iterations are off the ground, I think I'll get through the next chunk of work for my NBA salaries project.

***

One of my friends went on a spree of D&D multi-class character ideas the other week, which inspired me to do that myself. As he said, why work on your current character when you can make infinite more? My next idea is a paladin / warlock combination that I think could have a pretty intriguing backstory and arc. The idea is a holy warrior who gets corrupted and serves an underworld being who grants him access to dark magic previously unbeknownst to him. Although it's the same as my current character, a drow half-elf is probably the best race for the character because the stat modifiers line up with the classes and the drow heritage and associated stereotypes can be leveraged for the corruption backstory.

The narrative fits nicely with taking paladin for the first two levels and get the dueling fighting style to bolster the physical attacks. The third level would be my first in warlock, where you immediately take your otherworldly patron, and follow that up with taking my third paladin level and with it the Oathbreaker sacred oath. For storytelling purposes, 

***

What I'm Reading

* [The 15 Minute City](https://www.bloomberg.com/news/features/2020-11-12/paris-s-15-minute-city-could-be-coming-to-an-urban-area-near-you)
* [Transform your Data for Better Insights](https://visualnoise.substack.com/p/transform-your-data-for-better-insights)
* [Interview with Ira Kaplan of Yo La Tengo](https://toneglow.substack.com/p/0345-ira-kaplan-yo-la-tengo)
* This Census-Taker by China Miéville
* Go Tell It On The Mountain by James Baldwin

What I'm Watching

* The Mandalorian
* Clone Wars: The Mandalorian is tying in some characters and story lines from Clone Wars, so figured I'd watch it. Almost done with season one and so far, so good. Pretty solid and fun show.