---
layout: post
title:      "How my dog going viral gave me the perfect idea for My Rails Project"
date:       2020-06-12 02:59:34 -0400
permalink:  how_my_dog_going_viral_gave_me_the_perfect_idea_for_my_rails_project
---


TikTock has always been a mystery to me, I knew there were dance videos, weird challenges, and my niece loved it. It basicly seemed like a reincarnation of vine for generation Z. I always seemed interesting, but with all the other social medias out there I never thought to give it a try. Then COVID-19 hit and since I was stuck inside I decided to try it. So naturally, I decided to make videos about my amazing tiny pit bull, Ghost. Ghost is a full-grown pitbull that never fully grew and is now 7 years old and only weighs about 35 lbs. I knew how much joy she brought me, so I wanted to share that joy with everyone else. One of the special activities we like to do together is making homemade treats for her. I always like making dog treats for Ghost because she has food allergies, so this way I know exactly what is going in her treats without any surprises that may irritate her.

I started posting videos of my dog and her day-to-day life. However, it wasn't until I started posting videos of me making homemade dog treats that my TikTock account took off. The videos were popular, but then I posted a video of my dog enjoying a puppy popsicle that I made for her, and she went viral. Over a million views, 200,000 likes, and 700 comments all on one video. As I would go through the comments, I realized most of them wanted to know about the treat... how I made it, what ingredients I used, and how they could make something for their pet that was similar. People wanted to show their pets some love by making their favorite pet a custom treat. That's where I got the idea of an app for people to share and learn new homemade recipes for their pets.

I knew I would want the app to have users, pets, and recipes. I would have to join tables to accomplish all the different relationships that would be involved. Once I had all of my objects and relationships mapped out, it was time to start building my project. I began by building my users' table first, making sure my sign up and log in was working before I built any other models out. I then moved on to recipes and their relationship with users and pets. I accomplished this by making recipes a join table between a pet category and a user, then had the pet model belong to a user and a pet category. This took a lot of planning and making sure I had the right has_many and belong_to relationships. With the right plan, the rest of the code fell in place. The last part I needed to complete was the relationship between the recipes, ingredients, and measurements. I decided on this part, I would try doing a double-nested form. This was one of the most challenging things I have tried to do but knew I was up for the challenge. The part that I ran into trouble with was not the form but displaying the data. I finally realized that since it was a double-nested form that I would have to nest the way I showed the information. By iterating over the measurement array to show the ingredients. After that was finished, I just had to refactor my project and I was finished. I had a working app called Bone-Appetit for sharing new recipes with other pet lovers in the world.




