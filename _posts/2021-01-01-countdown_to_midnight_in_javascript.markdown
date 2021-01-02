---
layout: post
title:      "COUNTDOWN TO MIDNIGHT IN JAVASCRIPT"
date:       2021-01-02 02:07:32 +0000
permalink:  countdown_to_midnight_in_javascript
---


For the new year I decided to go over how to use a itteration in JavaScript to make a countown in JavaScript using a for loop. The first step is making a function that is creating a for loop but instead of counting up you need it to count down. To count down in a for loop you need to make some adjustments to your loop settings. In a normal loop you would set your index at 0, then add one to your index as long as the index is less than the length of the array. In the case of counting down you want to set your loop up so the index is equal to the array length minus one because the array starting point is zero. Then you want to set your counter for as long as your index is less than or equal to one. And the final instead of adding one you need to subract one each loop. 
```
for (i = list.length - 1; i >= 0; i--)
```

instead of 

```
for (i = 0; i >= list.length; i++)

```

Once you have your loop set up you can log each itteration as follows: 
```
console.log(list[i])
```


