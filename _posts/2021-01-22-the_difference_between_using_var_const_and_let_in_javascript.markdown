---
layout: post
title:      "The difference between using var, const, and let in JavaScript"
date:       2021-01-23 02:54:49 +0000
permalink:  the_difference_between_using_var_const_and_let_in_javascript
---

variables are very important in JavaScript and knowing the difference between them can save yourself from running into some unfortanate very unfortanate errors. In JavaScript there are three different ways to declare a variable by using var, const or let. Before ES6 was realeased using var was the only way to declare variables. 

```
var dogName= "Ghost"
dogName = "Goblin" 
console.log(dogName) 
=> Goblin 

``` 

the issue with using var to declare a variable however is that it makes the variable global so it can mess up your scope in your functions. You would be able to access dogName from anywhere in your file and change the value of it from anywhere in your file. Once ES6 came out we were introduced to let and const which is the prefered way to declare variables. 
When declaring a variable it always best practice to start by declaring your variable with const. Const will set the variable but also makes it so you can not change the value of that variable. 
```
const dogName = "Ghost";
dogName = "Goblin";
=> will throw a type error 
ERROR:
dogName = "Goblin";
        ^

TypeError: Assignment to constant variable.
```

It is good to have const variables to start because we wouldn't want to our variables getting reassigned or changed by accident down the road in our files. If we have a variable that we do want to change along the way or have the option to change as we go that is when we would use let. Let gives us the chance to reassign the variable later in our file. 
```
let dogName = "Ghost";
dogName = "Goblin";
console.log(dogName) 
=> Goblin
```
So as you can see it now lets us change the value of the dogName variable. A good example of when we would want to use let over const would be if we were having a number that will change when adding or itterating, like using a for loop and setting our counter. 
```
for(let i = 0; i < array.length; i++){
array[i]
}
```

In conclusion each variable type has it's pros and cons, but when in doubt try and use const and try to stay away from using var to avoid costly mistakes. 

