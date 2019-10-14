---
layout: post
title:      "Trial and Error the story of my first CLI GEM"
date:       2019-10-13 22:34:23 -0400
permalink:  trial_and_error_the_story_of_my_first_cli_gem
---


The thought of building my own CLI gem was extremely intimidating to me. I had been practicing every day for weeks, working on tests researching ruby terms, and practicing with other students online. However, I still felt like I wasn't completely ready for my first big project. No matter how I felt, it was time to put my knowledge to the test and build my first major project for Flatiron. After reviewing tutorials and going over old homework projects, I was ready to take all the information and skills I had learned and put it to work. For my CLI RubyGem, I decided to produce a list of the top ten box office results at a given time that gave an option to pick a film where you would be able to see the films Rotten Tomatoes score, audience score, and a brief synopsis of the film. 

The first step I took was making a list of everything I wanted my gem to have. From there, I could start to see the steps I would need to complete to get there. I knew I wanted to scrape two separate websites for each movie. I wanted to scrape Box Office Mojo for the movies rank, name and studio and then would use Rotten Tomatoes for the scores and synopsis of each movie on the list. I also decided to stick with the weekend of October 4th-6th to make sure my code wouldn't break if things drastically changed week by week when they updated their given sites. Once I knew what steps to take, I began building my CLI interface.

I kept it simple and direct so it would be user friendly and easy to navigate. Once I had my basic code in place, I added placeholder data to make sure everything worked before I began scraping anything. I got stuck at two separate parts during this section. The first ended up being a minor mistake of some misplaced def and end components which once I figured it out was an easy fix. However, the other was more difficult because I couldn't get my bin console to work. It kept showing error after error. It took me an entire day but I dove deep and finally found a video where it showed me that I needed to delete some "required" lines in my gem file. I couldn't believe after all the time I spent on it that it was such a simple fix. Once my console was finally working, it was time to start scraping. 

The two major websites I scraped were Rotten Tomatoes, which was very straight forward to scrape with very detailed selectors, and Box Office Mojo, which was much more difficult to scrape given that it was in table format and had no distinctive class or ID selectors. To scrape the table, I turned the table's data into an array where I used .map and .text to break up the information. I was then able to get the specific information through its index number in the newly created array. Once I was finished scraping, I went through and started to clean up all my code. I wanted to make sure it was as clean as possible by using the DRY techniques I learned. Once it was all cleaned up and functioning properly, I was finally finished. I couldn't believe I just built my first CLI gem! 


