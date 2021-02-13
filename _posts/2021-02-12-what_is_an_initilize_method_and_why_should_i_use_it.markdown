---
layout: post
title:      "What is an initilize method and why should I use it?"
date:       2021-02-13 00:35:52 +0000
permalink:  what_is_an_initilize_method_and_why_should_i_use_it
---


The initialzie method is a great tool you can use when building out your classes in Ruby. When you make a new instance of your class you can use this method to give your new object arguments without throwing errors and setting your initial values for your object. For example if we have a dog class and want to be able to assign a name and owner when it is created. If we don't have that initilize method we will get an argument error when we try to create a new dog object. 

```
class Dog

end 

Dog.new("Fido", "Jesse")

=> ArgumentError (wrong number of arguments (given 2, expected 0))

```

If we add the initialzie method in our class method then when we will no longer get the argument error and will be able to create our dog object. 

```
class Dog

    def initialize(name, owner)
        
    end

end

Dog.new("Fido","Jesse")

 => #<Dog:0x00007fbe83a36170> 
```

we may have created the dog object but initializing it doesn't save our name and owner attributes. If we want to save our attributes we will have to save them as variables and if we want to use these variables in other methods it might be a good idea to save them as instance variables. 
```
class Dog

    def initialize(name, owner)
        @name = name
				@owner = owner 
    end

end

 Dog.new("Fido", "Jesse")
 
 => #<Dog:0x00007fa3538a3fb0 @name="Fido", @owner="Jesse"> 
```

Now our variables are saved in our object but how do we access them? If we save our dog object as a variable and try getting the name or owner it will return not available. We will needto write getter and setter methods to accomplish this. I will discuss writing getter and setter methods next week in my next blog. 





