---
layout: post
title:      "Finding the Best Winner in Drag Race HERstory with JavaScript Part 2"
date:       2021-01-15 21:34:40 -0500
permalink:  finding_the_best_winner_in_drag_race_herstory_with_javascript_part_2
---


![](https://attitude.co.uk/media/images/2020/04/drag_race_main.jpg.750x400_q85_box-0%2C0%2C1500%2C800_crop_detail.jpg)


[**PART 1:** ](https://cep104.github.io/finding_the_best_winner_in_drag_race_herstory_with_javascript_part_1)

Now that we have the winners object ready to go it is time to start setting up a function to help us determine who the ultimate winner of Drag Race is based on points. First I would have to come up with a system for the points, when I made teh data I made two seperate keys in the winners object, one for wins and one for losses. Inside of those there is categories for major wins/losses and minor wins/losses. I decided that each major win will count as 2 points since they are valued more where minor wins will count as just a single point. 
```
wins: {
      maxiChallengeWins: 2,
      miniChallengeWins: 0,
      timesInTop: 1,
    },
    losses: {
      timesPlacedLow: 0,
      timesInBottom: 1,
    },
```

Next I would have to establish the skeleton structure for my function and make it be able to pass in my winners object. 
```
const youreAWinnerBaby = () => { }
```
Now that I have my function set up I can start extracting data from it. To be able to get all the values from each winners object I can set a variable for all of the winners objects values and itterate over them to get each indivual queens information. 
```
let winnerInfo = Object.values(winners);
for (i = 0; i < winnerInfo.length; i++) {
    let queen = winnerInfo[i];
		}
```
Once I have each indivual queens information I can change my data for wins and losses and be able to add the necessary points. I want to access each win and loss category and double the big wins and losses while keeping the smaller wins and losses the same. Since there are two seperate small win categories I will also add those together for one total for small wins and assign all of them to variables. 
```
const bigLoss = queen["losses"]["timesInBottom"] * 2;
const bigWin = queen["wins"]["maxiChallengeWins"] * 2;
const smallWin =
queen["wins"]["timesInTop"] + queen["wins"]["miniChallengeWins"];
const smallLoss = queen["losses"]["timesPlacedLow"];
```
Lastly after I have all my data set and the points valued correctly I can run a final total of wins - losses for each queen along with their name. 
```
let queenName = queen["name"];
const totalScore = bigWin + smallWin - (smallLoss + bigLoss);
```

I will want to store these new totals and the queens names in a new object in an array, so I will be able to access and compare all my new data. To do this I will need to define an empty array outside of the itteration then push the new data inside the new array with each itteration. This will give us a new object to work with next time to compare all of the new scores and identify who they belong too. 
```
const youreAWinnerBaby = (winners) => {
  // console.log(winners);
  let finalScores = [];
  let winnerInfo = Object.values(winners);
  for (i = 0; i < winnerInfo.length; i++) {
    const queen = winnerInfo[i];
    let queenName = queen["name"];
    const bigLoss = queen["losses"]["timesInBottom"] * 2;
    const bigWin = queen["wins"]["maxiChallengeWins"] * 2;
    const smallWin =
      queen["wins"]["timesInTop"] + queen["wins"]["miniChallengeWins"];
    const smallLoss = queen["losses"]["timesPlacedLow"];
    const totalScore = bigWin + smallWin - (smallLoss + bigLoss);

    finalScores.push({ queenName, totalScore });
  }
 return finalScores
};
```

Next week I will go over making my final function to go over the new array of objects and be able to tell us who is the ultimate drag queen winner based off of points. 
