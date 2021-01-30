---
layout: post
title:      "Finding the Best Winner in Drag Race HERstory with JavaScript Part 3"
date:       2021-01-30 03:15:33 +0000
permalink:  finding_the_best_winner_in_drag_race_herstory_with_javascript_part_3
---


![](https://cdn.substack.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ffbf8a487-92ba-41e4-a942-1bd4fd517491_500x281.gif)
In the previous blog we got our new array which has each queen stored as an object that contains their final score for and their name so we can display the winner. 

```
finalScores =>
[
  { queenName: 'Bebe Zahara Benet', totalScore: 3 },
  { queenName: 'Tyra Sanchez', totalScore: 9 },
  { queenName: 'Raja', totalScore: 9 },
  { queenName: 'Sharon Needles', totalScore: 8 },
  { queenName: 'Jinkx Monsoon', totalScore: 10 },
  { queenName: 'Bianca Del Rio', totalScore: 12 },
  { queenName: 'Violet Chachki', totalScore: 7 },
  { queenName: 'Bob the Drag Queen', totalScore: 5 },
  { queenName: 'Sasha Velour', totalScore: 9 },
  { queenName: 'Yvie Oddly', totalScore: 5 },
  { queenName: 'Jaida Essence Hall', totalScore: 7 }
]
```

Now that we have the array complete we want to rearrange the queen objects based on their total score. There is a great method for arrays that we can use called sort that will come in handy in this situation. Sort is perfect for putting the queens in the order we want because you can sort based on values. You can use the sort() method of Array, which takes a callback function, which takes as parameters 2 objects contained in the array (which we call a and b):
```
finalScores.sort((a, b) =>a.totalScore > b.totalScore ? -1 : 1)
```
When we return -1, the function communicates to sort() that the object a takes precedence in sorting over the object a. Returning 1 does the opposite. So after all the sorting has finished we store the new sorted array as a variable and get our new sorted array 
```
topQueen =>
[
  { queenName: 'Bianca Del Rio', totalScore: 12 },
  { queenName: 'Jinkx Monsoon', totalScore: 10 },
  { queenName: 'Tyra Sanchez', totalScore: 9 },
  { queenName: 'Raja', totalScore: 9 },
  { queenName: 'Sasha Velour', totalScore: 9 },
  { queenName: 'Sharon Needles', totalScore: 8 },
  { queenName: 'Violet Chachki', totalScore: 7 },
  { queenName: 'Jaida Essence Hall', totalScore: 7 },
  { queenName: 'Bob the Drag Queen', totalScore: 5 },
  { queenName: 'Yvie Oddly', totalScore: 5 },
  { queenName: 'Bebe Zahara Benet', totalScore: 3 }
]
```
Now that we have our queens sorted from top to bottom based on scores it's time to display the winner. We can do that by having our function return the first queen object from the array. So we will create an H1 and putting its innerHTML as the winner! 
```
const h1 = document.createElement("h1");
h1.innerHTML = `${topQueen[0].queenName} is the winner!`;
```
...........and our winner is........................
BIANCA DEL RIO!!! 
![](https://i.imgur.com/SVxrr5e.gif)
Thanks to JavaScript I was able to make a function that would show me who would win an all winners season on
RuPaul’s Drag Race based on their previous wins. Obviously, in a real winners season, there would be many more factors that would come into play but till they make an all-winners season this function will help decipher who might actually come out on top. 



