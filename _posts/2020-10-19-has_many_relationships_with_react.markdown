---
layout: post
title:      "Has many relationships with React"
date:       2020-10-19 00:30:10 -0400
permalink:  has_many_relationships_with_react
---


For my React/Redux project I knew I wanted to help the shelter I volunteered at. I could do this by making a foster database to keep track of what dogs a foster currently had. The shelter had all the information but was keeping it on an excel sheet, and wasn't getting updated as often as it should have been. I wanted to create an app where a shelter could easily add fosters to their database then add and delete dogs from that fosters page. I also wanted there to be a database of all the dogs at the shelter for them to look through as well. 
I started the project by making the backend. I made the API with the has many belongs to the relationship set between a caretaker and a dog. Once I finished with the backend setting up the models, controllers, and serializers I moved on to starting the frontend of my project. I had never worked with a have many relationship with React before so I knew It was going to be tricky. I decided on setting up my dog form within my caretaker page. I had set up my relationship for all dogs to be created through a caretaker on the backend so that the logic would be easier to follow. This all worked great till I wanted to set up a list of all the dogs in the shelter and individual dog pages as well. 
When making my routes I wanted to be able to grab the information from the dogs API instead of the caretakers API so it would be more CRUD based. This is where I ran into a huge issue when I create a dog through caretakers that the dog would immediately update on the caretaker's page. However, I would need to refresh for the same information to pop up on the individual dog and all dog pages. I started breaking everything down and brainstorming. I finally realized that it was because I was creating my dogs on the backend through caretakers, instead of creating them through dogs. This was a tough lesson I learned in the separation of concerns and why it's so important. I thought I could take the easy way out and just do everything in one spot but with everything, I wanted to accomplish realized that was not possible. 
To fix the issue I had to do a lot of backtracking and needed some help from my cohort leader. I started the fix with the backend. I realized I would have to create dogs through dogs and then attach them to a caretaker. I also changed the settings for deleting dogs as well. 
```def create
        @dog = Dog.new(dog_params)
        @dog.caretaker = Caretaker.find(params[:caretaker_id])
            if @dog.save
                render json: @dog
            else
                render json: {error:'Error creating Dog'}
            end
    end```
		
		
once the backend was fixed I had to change the way the dogs were displayed and created from the frontend as well. When I create a dog I would assign the caretaker's id when submiting the dog form. 
```
this.props.createDog({ dog: this.state, caretaker_id: this.props.caretaker.id})
```
Then when my app was sending a post request it would be to the dog API instead of the caretakers API like I was doing previously. This way when a dog was created, it would automatically update anything that was run through the dog API. This solution fixed my issue since the API that was getting changed was the only API that was dealing with dogs. So by separating my concerns and re-evaluating my code I was able to have a successful application without refreshing. 
