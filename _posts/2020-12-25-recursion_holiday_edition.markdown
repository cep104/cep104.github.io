---
layout: post
title:      "Recursion Holiday Edition! "
date:       2020-12-26 02:55:22 +0000
permalink:  recursion_holiday_edition
---


While learning JavaScript the one subject that always seemed to trip me up was recursion. I would use it and be able to memorize the steps of using it but never really fully understood what I was doing with it. This week I decided to really dive deep and focus on understanding what was going on under the hood and break it down for myself. First I decided to break down the definition of what recursion was, the most simple explanation is that it is a function that calls on itself. Sounds simple enough but I know from first-hand experience how complicated this can get. When setting up an example for myself to follow I decided to write some pseudo code first. Since it's the holiday season, I decided to make my example about receiving a present, but little did you know this present is from your jerk older brother. He has put your present inside multiple boxes which you will have to open one by one till you finally can get to your present. This is a great example to use recursion on because we do not know how many boxes we will need to go through. It also has a stopping point(base case statement) which is when we reach the present. 

```
pseudo code:

let present = [[[[[ "present"]]]]]

function getGift(present){

if(we've gotten to the gift) ----- make a base case statement
return 'finally my gift!' ---------- if condition is met return string
 else  ---------------------------- if the present is not found
getGift(the smaller box) ------- run the remainder of the present through again
---------------------------------- keeps going and going and going till base case is met. 
 }

```

When looking at my pseudo code, the first thing I needed to do was determine how to set my base case. I knew I wanted to check if the code finally hit the present, but determining the best way to do this would be tricky. The first thing I tried was setting up an if/else statement where I would check each time to see if it's an array. Once it wasn't an array, it would return "finally got my present."The only issue with this is that I couldn't think of a good way to keep reducing the array each time to get to the present string. I started to do some research on how to use recursion while using nested arrays and decided to try using reduce instead. I would run, reduce on the array, would have the starting value be an empty array which the acc argument will be set at and present would represent the current iteration of the array. 

```
return array.reduce((acc, present) =>{}, [])
```

The next part is where I had to decide how I wanted to use recursion and what my base case would be. After some trial and error, I decided on checking to see if the current present was an array. I set up a ternary statement so if it was an array I would run the flat method again if it were not an array then I would just return the present. We do this by taking the empty array and running .concat with an argument of our ternary. This way if it is an array, it will run the now smaller array with recursion through the function again and again till it is no longer an array and then will in fact return our statement instead. 

```return array.reduce((acc, present) => {
    return acc.concat(Array.isArray(present) ? flat(present) : console.log('finally my gift!'));
  }, []);
	
	```
	
In the end, when we put it all together, I have a function that uses recursion to sort out a nested array and returns a statement when the base statement of the recursion is finally met(it is no longer an array.) While working on this, I was able to understand recursion better and get more comfortable being able to use it for different tasks. 

```
function flat(array) {
  console.log("haha still not the present");
  //   console.log(array);
  return array.reduce((acc, present) => {
    return acc.concat(Array.isArray(present) ? flat(present) : console.log('finally my gift!));
  }, []);
}

```
