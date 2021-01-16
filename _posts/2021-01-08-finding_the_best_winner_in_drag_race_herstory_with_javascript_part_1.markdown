---
layout: post
title:      "Finding the Best Winner in Drag Race HERstory  with JavaScript Part 1"
date:       2021-01-08 23:24:22 -0500
permalink:  finding_the_best_winner_in_drag_race_herstory_with_javascript_part_1
---

![](https://res.cloudinary.com/jerrick/image/upload/fl_progressive,q_auto,w_1024/xpfukdrt1yzhdnsk69en.jpg)


RuPaul’s Drag Race is one of if not the best reality television show ever made. It has fashion, comedy, stunts, and of course all the drama you could ask for. One thing it has never had before is an all-winners season. So, I decided to use the power of JavaScript to find out who would win based on previous stats and rankings. For the purpose of simplicity, I chose only the original Drag Race so not All Stars and no world seasons. To be able to make an application that would tell me who the best Drag Queen winner of all time I would first need to collect data on all the winning queens. In JavaScript there are many ways to store data but because I would be having multiple factors associated with every queen a object seems like the best way to store all the data. To store data inside an object you need sets of keys with values. This way we will have all are data stored is in one big winners object with each queen objected nested inside the original object. 

****SPOILER WARNING***********
```
const winners = {
  bebeZaharaBenet: {},
	tyraSanchez: {},
	rajaGemini:{},
	sharonNeedles:{},
	jinxMonsoon:{},
	biancaDelRio:{},
	violetChachki:{},
	bobTheDragQueen:{},
	sashaVelour:{},
	aquaria:{},
	yvieOddly:{},
	jaidaEssenceHall:{}
	
```

Now that I had all my drag queen winner objects it was time to start giving them their own keys and values. I knew I wanted to have a way to access their full name, some memorable quotes, their wins and their losses.  

```
const winners = {
  BebeZaharaBenet: {
    name: "Bebe Zahara Benet",
    seasonWon: "S1",
    memorableQuotes: [
      "Mother, another day; another slay. Who's first?",
      "Rrrrra-ka-ta-ti-ti-ta-ta",
    ],
    wins: {
  
    },
    Losses: {

    },
  },
```
For their wins and losses I decided on factoring in five things so new that wins and losses would also have to be their own objects. I also wanted to make sure they were numbers so I would be able to compare contrast them later down the road. 
```
  BebeZaharaBenet: {
    name: "Bebe Zahara Benet",
    seasonWon: "Season 1",
    memorableQuotes: [
      "Mother, another day; another slay. Who's first?",
      "Rrrrra-ka-ta-ti-ti-ta-ta",
    ],
    wins: {
      MaxiChallengeWins: 2,
      MiniChallengeWins: 0,
      TimesInTop: 1,
    },
    Losses: {
      TimesPlacedLow: 0,
      TimesInBottom: 1,
    },
  },
```
Now that I had all my data stored I would be ready to access anything I needed, for example if I wanted to see what season Bebe Zahara Benet won all I would have to do now is select it using the winners objects keys. 
```
Winners["BebeZaharaBenet"]['seasonWon"]
//would return the value "Season 1"
```
next week I will take this newly created object to start making a function to display the ultimate winner. 

