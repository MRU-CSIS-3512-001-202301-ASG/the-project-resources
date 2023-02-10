# Site Use Summary

## Admin Site

The idea here is that a person working for the government needs to log in to your site and change the ratings on photos to/from 3 as a sneaky way to indicate to field agents whether the lat/long of those photos is actually a dead drop location or not.

Use your imagination here a bit: if **you** were such a person, how would **you** like to see the necessary information (thumbnail, country, city, latitude, longitude, and rating) for all the photos in the database displayed? Remember: you're not there to look at the pretty pictures - they don't mean anything to you: they're simply a means to hide a latitude and longitude. Instead, you're there to set the rating of a photo. That's it.

The ability to filter by country, city, and rating is meant to make life easier for such people.

The ability to sort and "remember" the sort order via cookies is an example of a not-really-necessary feature that users often ask of developers: a feature they _think_ would be neat, but will likely not end up being used much, if at all. Welcome to dealing with users. :)

## Public-Facing Site

This site is actually targeted to TWO different types of users: unsuspecting folks who _think_ they're looking at a travel photo site, and field agents who are going to the site to find out coordinates of dead drops in the city they're in.

### User Group 1: The Unsuspecting Masses

To be useful to these users, you want to make their site experience pleasant and intuitive. 

They'll want to do things like:
    
- Browse through all the photos.
- Look up photos just from one country. Maybe they have a particular country in mind, or perhaps they'd just like to browse through all the countries instead, choosing ones that catch their interest.
- Get information about different countries and cities, because geography and travel is fun.
- Look more closely at specific pictures and get more information about it.

### User Group 2: The Field Agents

Field agents have one task in mind: quickly and easily find out the location of dead drops in their city of choice. This means they'll likely just type in the name of their city of choice, look for photos until they find one that only has a rating of 3, click on it, and then find out what the latitude and longitude is from the Single Photo View.

