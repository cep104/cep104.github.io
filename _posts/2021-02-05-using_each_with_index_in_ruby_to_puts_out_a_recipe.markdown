---
layout: post
title:      "Using 'each_with_index' in Ruby to puts out a recipe"
date:       2021-02-06 03:25:22 +0000
permalink:  using_each_with_index_in_ruby_to_puts_out_a_recipe
---

![](https://media1.giphy.com/media/VmVlV9VCul2nK/giphy.gif)

Sometimes when we when we iterate through an array in Ruby we want to include an index number, we can accomplish this by using the .each_with_index method. For example if we have a an array with steps for a recipe and we want to use the index numbers to show what number each step represents. 
```
chicken_soup_recipe = ["Melt butter in a large stockpot or Dutch oven over medium heat. Add onion, carrots and celery. Cook, stirring occasionally, until tender, about 3-4 minutes. Stir in garlic until fragrant, about 1 minute.", "Whisk in chicken stock and bay leaves; season with salt and pepper, to taste. Add chicken and bring to boil; reduce heat and simmer, covered, until the chicken is cooked through, about 30-40 minutes. Remove chicken and let cool before dicing into bite-size pieces, discarding bones.", "Stir in chicken and pasta and cook until tender, about 6-7 minutes.", "Remove from heat; stir in parsley, dill and lemon juice; season with salt and pepper, to taste.", "Serve immediately."]
``` 
The way each_with_index works it takes each item in the array one by one similar to the .each method but what it also does it takes the index of the item along with it. When we use the eachwithindex method it will take in two parameters one for the index number of the array and one for each item.  
```
def print_recipe(recipe)
recipe.each_with_index do | recipe_item, index |
puts "#{index}. #{recipe_item}"
end
end

=>
0. Melt butter in a large stockpot or Dutch oven over medium heat. Add onion, carrots and celery. Cook, stirring occasionally, until tender, about 3-4 minutes. Stir in garlic until fragrant, about 1 minute.
1. Whisk in chicken stock and bay leaves; season with salt and pepper, to taste. Add chicken and bring to boil; reduce heat and simmer, covered, until the chicken is cooked through, about 30-40 minutes. Remove chicken and let cool before dicing into bite-size pieces, discarding bones.
2. Stir in chicken and pasta and cook until tender, about 6-7 minutes.
3. Remove from heat; stir in parsley, dill and lemon juice; season with salt and pepper, to taste.
4. Serve immediately.
```

But oh no! When we run the file we notice that our recipes are starting wtih a zero instead of one. This is caused because when we count arrays we always start at zero. All we would have to do to fix this is just add one to the index in our puts statement. 
```
def print_recipe(recipe)
recipe.each_with_index do | recipe_item, index |
puts "#{index + 1}. #{recipe_item}"
end
end
=> 
1. Melt butter in a large stockpot or Dutch oven over medium heat. Add onion, carrots and celery. Cook, stirring occasionally, until tender, about 3-4 minutes. Stir in garlic until fragrant, about 1 minute.
2. Whisk in chicken stock and bay leaves; season with salt and pepper, to taste. Add chicken and bring to boil; reduce heat and simmer, covered, until the chicken is cooked through, about 30-40 minutes. Remove chicken and let cool before dicing into bite-size pieces, discarding bones.
3. Stir in chicken and pasta and cook until tender, about 6-7 minutes.
4. Remove from heat; stir in parsley, dill and lemon juice; season with salt and pepper, to taste.
5. Serve immediately.
```

Now we have a method that can puts out our recipe for chicken noodle soup with the step numbers. 
![](https://media1.tenor.com/images/82fba9749d2d13f65acaecbdfcf4c254/tenor.gif?itemid=5407173)







