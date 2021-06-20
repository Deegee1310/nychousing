# nychousing

What the project does	 <br />
The idea of this project was to browse through potential airbnb listings in NYC and find a suitable housing for me, which depends on limitations and my own preferences. <br />
 <br />

Why the project is useful <br />
Code can be transfered to any other listings.csv provided by airbnb. Limitations and personal preferences have to be defined in the limitations section. <br />
 <br />

How users can get started with the project  <br />
All you need is a listings.csv file which you can find here http://insideairbnb.com/get-the-data.html .  <br />
 <br />

Who maintains and contributes to the project  <br />
For now there is no maintainance of code.

Overview of files: <br />
- blogpost -> Text for users to understand the idea rather than the actual code.
- jupyter notebook -> Code to recreate the housing recommendation

Libs used: <br />
- Pandas which offers data structures and operations for manipulating numerical tables and time series <br />
- Numpy adding support for large, multi-dimensional arrays and matrices <br />
- Math provides access to the mathematical functions defined by the C standard. <br />

Key result:
Due to restrictions that apply for my personal case (availability, price and room type of housing), the potential housings in NYC list decreased by 76% from 36905 to 8870.
Respecting my restrictions and also my personal preference to have a housing located near my work, I found a great place just 200m from work and for only 95 USD per night!

Big thanks to airbnb providing the needed dataset.
Airbnb Open Data: http://insideairbnb.com/get-the-data.html 
