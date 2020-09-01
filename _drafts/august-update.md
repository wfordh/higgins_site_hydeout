---
layout: post
title: August Update
excerpt: ''
date: 
last_modified_at: 
categories: []
tags: []
comments: false

---
There's a Q2 Review post sitting in my drafts, but I haven't had the time to finish it and the thoughts motivating this post are sufficiently different to have their own. Perhaps I'll go back and finish it, perhaps not. The last couple of months have been pretty busy, though. My partner and I moved in together this month, so it's been a lot of unpacking things and getting used to being together after spending very little time together before due to social distancing stuff. We went to her hometown for a bit, but are back in the city now. American team sports are back, which means a lot of my time is taken up watching them, for better or worse. And I continue to prioritize things like reading another random book over writing something. 

But the ideas have been swirling around in my head and my hand is forced, so to speak, by some conditions around American sports. The fantasy baseball playoffs are starting up and my fantasy football draft is a week from tomorrow, so it's the best time to try to cram way too much work into too little time and update some tooling. Thankfully this acts as a bit of a forcing function on what work is important and should be prioritized. Let's not waste any of that precious time here and dive right into it.

# Fantasy Baseball

## Ottoneu Tools

I play fantasy baseball on [Ottoneu](ottoneu.fangraphs.com) in a salary cap, dynasty format. There's a ton of cool data and ways that I can think of using it to help me make decisions during the season and offseason. The data directly on the Ottoneu website that I'd like to investigate include:

* H2H Schedule: One of my leagues is a H2H league (as opposed to a pure points league) and I'd like to hybridize it a bit and see how each team would perform each week if they played every other team. The current utility is limited since playoffs have already started, so I'll just save the raw data and shelve this one for now.
* Transactions: All of the auctions and trades have great information, and one can get a feel for how aggressive the other players are in your league. It could also be combined with salary cap and roster structure data.
* Average Salaries: This is pretty much already built into Ottoneu, so it's more a matter of pulling it down so I can use the data locally.

## Statcast Tools

There's so much great data available in Statcast. Unfortunately, there's no API and while it's possible to get fairly granular data, that would be a monstrous task. Fortunately, there's already some stuff on it in [`pybaseball`](https://github.com/jldbc/pybaseball) and I'd love to add to it. Most of the use for this data is in combining it with the roster information in Ottoneu to do things like find the correlation between exit velocity and salary or identify potential targets. I'm sure there are great uses for it on the pitching side, but I'm more familiar with the hitting stats and will likely focus there.

## FanGraphs Tools

Similarly to Statcast, it's a bit of a pain to get data from FanGraphs. Some functionality can be found in `pybaseball` (and its forks) though I'll need to customize