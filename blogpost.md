Blogpost: 

<h1> How to find a suitable apartment for you in airbnb based on your own preferences</h1>

<img src="https://images.unsplash.com/photo-1513107358949-b21c1c3906eb?ixid=MnwxMjA3fDB8MHxzZWFyY2h8OXx8bmV3JTIweW9yayUyMGNpdHl8ZW58MHx8MHx8&ixlib=rb-1.2.1&w=1000&q=80" alt="Italian Trulli">

I used the NYC Airbnb Dataset for this blog post. You can find the web address of the dataset in References section below. As part of the Airbnb Inside initiative, the dataset describes the listing activity of homestays in NYC.

<h2>Motivation behind this project focuses on answering following questions:</h2>
Q1: Which apartments are affordable (within my budget) <br>
Q2: Is it available in certain timeframe? <br>
Q3: How far to walk to work? <br>
<br>
<h2>Before answering the questions, we need some background information, or limitations to respect!</h2>
<br>
Example: David wants to work in NYC for 2 months<br>
To ensure a personalized recommendation for my search, we need my preference input to kickoff the query.<br>
<br>
My job gives me the following limitations for the query:<br>
- I would like to stay for at least 40 days<br>
- My allowed budget is 440 per night<br>
- Entire appartment<br>
<br>
For my personal choice:<br>
- I would like to take the distance to work into account, as I do not like to commute.<br>
- We consider the location of my work location as another feature for our project<br>
<br>
As mentioned, for me, the distance to work is pretty important, but for others it may not be.<br>
In the code, I installed a score for the importance of the price and distance to work, so that it is more generetic and can be applied to other preferences.<br>
I determined the score of the importance of features price and distance to work on a scale from 1-5, where 5 is very important and 1 vice versa.<br>
Price score = 1 , since I do not care about the price as long as it within my budget.<br>
Distance score = 5 since I really do not like commuting. <br>

<h2>Q1 and Q2:</h2>
Due to the restrictions of availability, price and room type, the data shrinks by 76%. But do not worry, we still have thousands of housing options to investiage.

<h2>Q3:</h2>
In order to calculate the distance between the housing option and work, I used the haversine distance (HD) and attached it as a columns in the data frame. HD is defined as the following:
The Haversine (or great circle) distance is the angular distance between two points on the surface of a sphere. The first coordinate of each point is assumed to be the latitude, the second is the longitude, given in radians. The dimension of the data must be 2.

<h2>Results:</h2>
R1: Prices
The average price per night is 163 USD. It is cool that we see kind of a normal distribution here right? A little left skewed but still. 
Maybe I can save some money since 163 USD average price is way below my budget. We will see. <br> <br>

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
