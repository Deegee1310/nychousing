Blogpost: 

<h1> How to find a suitable apartment for you in airbnb based on your own preferences</h1>

I used the NYC Airbnb Dataset for this blog post. You can find the web address of the dataset in References section below. As part of the Airbnb Inside initiative, the dataset describes the listing activity of homestays in NYC.

Motivation behind this project focuses on answering following questions:
Q1: Which apartments are affordable (within my budget)
Q2: Is it available in certain timeframe?
Q3: How far to walk to work?

Before answering the question, we need some background information, or limitations to respect!

Example: David wants to work in NYC for 2 months
To ensure a personalized recommendation for my search, we need my preference input to kickoff the query.

My job gives me the following limitations for the query:
- I would like to stay for at least 40 days
- My allowed budget is 440 per night
- Entire appartment

For my personal choice:
- I would like to take the distance to work into account, as I do not like to commute.
- We consider the location of my work location as another feature for our project

As mentioned, for me, the distance to work is pretty important, but for others it may not be.
In the code, I installed a score for the importance of the price and distance to work, so that it is more generetic and can be applied to other preferences.
I determined the score of the importance of features price and distance to work on a scale from 1-5, where 5 is very important and 1 vice versa.
Price score = 1 , since I do not care about the price as long as it within my budget.
Distance score = 5 since I really do not like commuting. 

Q1 and Q2:
Due to the restrictions of availability, price and room type, the data shrinks by 76%. But do not worry, we still have thousands of housing options to investiage.

Q3:
In order to calculate the distance between the housing option and work, I used the haversine distance (HD) and attached it as a columns in the data frame. HD is defined as the following:
The Haversine (or great circle) distance is the angular distance between two points on the surface of a sphere. The first coordinate of each point is assumed to be the latitude, the second is the longitude, given in radians. The dimension of the data must be 2.

Results:
R1: Prices
The average price per night is 163 USD. It is cool that we see kind of a normal distribution here right? A little left skewed but still. 
Maybe I can save some money since 163 USD average price is way below my budget. We will see.

R2:The average distance within my limitations to the query are around 8km. But I can also see from the distribution that most of the housing are actually only 5km away.
To be honest that is still a little far for my personal preference. Let us see what we can do about that.

Adding the evaluation column by calculating the housing_price * personal_price_importance + housing_distance * personal_distance_importance.

By respecting my stated questions and preferences for location distance to work and affordability,
it seems like I will check out the Modern + Clean Apartment in Downtown Manhattan!! for 95$ per night!

Maybe I can work out a deal with my employer, such that I can keep the savings from my max budget of housing expenses!
Would love that ;)

References
Airbnb Open Data: http://insideairbnb.com/get-the-data.html 
Github: https://github.com/Deegee1310/nychousing
