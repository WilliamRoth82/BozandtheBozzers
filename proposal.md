# Research Proposal: Sea Level Rise effect on Coastal Housing Prices
By BozandtheBozzers: 
Andrew Bosland, Will Rothpletz, Carter Karinshak, and Linh Thai

## Research Question

Over the past two decades, climate change has become a topical issue that many worry about due to its implications on our planet and quality of life. One effect of increasing temperatures from climate change is the melting of the polar ice caps which leads to high amounts of fresh water flooding our oceans and the sea level gradually rising. With this sea level rise comes numerous problems, one of which is its impact on coastal cities or homes. As sea levels rise, they erode beaches, reduce usable land, and jeopardize the integrity of structures that were not built in accordance with much higher sea levels. The rising sea level is a major concern for many coastal home owners, and we plan to analyze this problem further. 

In this project, we want to analyze the correlation between the gobal change in sea level and the listing prices for U.S. houses in coastal regions in an
attempt to measure the relationship bewteen rising sea levels and coastal housing prices. Using our results we want to look at the difference in listing prices changes between the average U.S. home listing price and the coastal U.S. home listing prices to see how changes in sea levels effected the two groups. From the differences, we are hoping to be able to better explain how much changes in sea level are actually effecting the listing value of coastal homes. Finally, using all of our results from our analysis, we will attempt to predict how coastal property listing values will be effected given the estimated rise in U.S. coastal sea waters. Data on our estimated rise over the next 10 years is provided by the National Oceanic and Atmospheric Administration.

To answer our question, we obtained from FRED the coastal U.S. housing listing prices for the past 6 years on numerous, prominent U.S. coastal cities as well as the overall average U.S. home listing price. Addtionally, from Kaggle we were able to locate data on global sea level rises over the past two decades. In this dataset, the primary variable we will be using for analysis is GMSL_noGIA which is the global mean sea level (Global Isostatic Adjustment (GIA) not applied) variation (mm) with respect to 20-year TOPEX/Jason collinear mean reference. Not accounting for GIA means that we will not be accounting for possible movements in the earths crust under or around ice caps. Addtionally, the 20-year TOPEX/Jason collinear mean reference is a prominently used study that examines historic sea levels rises and predicts a trend of a rise of 3.3 mm/year in sea level. 

For our hypotheses, we predict that that a rise in sea level has a statistically significant impact on the listing prices of homes in U.S. coastal cities. to explore this hypothesis, our null hypothesis is that the average change in coastal city home listing prices associated with a 1 mm rise in global sea levels is equal to 0, or β1 = 0, with all other variables held constant. Our alternative hypotheses therefore tests if this association is not equal to one, or β1 ≠ 0, and if some correlation is present in this relationship. 


## Necessary Data
This section should cover:

What does the final dataset need to look like (mostly dictated by the question and the availability of data):

What is an observation, e.g. a firm, or a firm-year, etc.

What is the sample period?

What are the sample conditions? (Years, restrictions you anticipate (e.g. exclude or require some industries)

What variables are absolutely necessary and what would you like to have if possible?

What data do we have and what data do we need?

How will we collect more data?

What are the raw inputs and how will you store them (the folder structure(s) for each input type)?

Speculate at a high level (not specific code!) about how you’ll transform the raw data into the final form.
