![](pics/caribbean-beach-wide.jpg)
<span style="color:lightblue; font-size:36px; font-weight:bold;">Welcome to Bozland! Home of the Bozzers</span> <br>

## Table of contents
1. [Introduction](#introduction)
2. [Our Data](#dataclean)
3. [Methodology](#meth)
4. [Analysis of Our Findings](#section2)
    1. [Price History](#subsec2-1)
    2. [Price Distribution](#subsec2-2)
    3. [Mean Price Coastal vs. Inland](#subsec2-3)
    4. [Price vs Sea Level](#subsec2-4)
    5. [Correlation](#subsec2-5)
5. [Future Predictions](#section3)
6. [Summary](#summary)

## Introduction  <a name="introduction"></a>

Over the past two decades, climate change has become a topical issue that many worry about due to its implications on our planet and quality of life. One effect of increasing temperatures from climate change is the melting of the polar ice caps which leads to high amounts of freshwater flooding our oceans and the sea level gradually rising. With this sea level rise comes numerous problems, one of which is its impact on coastal cities or homes. As sea levels rise, they erode beaches, reduce usable land, and jeopardize the integrity of structures that were not built in accordance with much higher sea levels. The rising sea level is a major concern for many coastal homeowners, and the main goal of this project is to analyze this problem further.

In our initial proposal, we wanted to analyze the correlation between the global sea level change and the listing prices for U.S. houses in coastal regions in an attempt to measure the relationship between rising sea levels and coastal housing prices. To answer this question we looked at the difference in median home listing prices for houses in different zip codes from the same coastal region. By comparing housing prices for zip codes that are directly on the coastline with those that are further inland, we can analyze if there is a correlation between housing price and sea level.

We also intended to examine the magnitude of impact on housing prices given how further inland a particular coastal zip code is, and to predict coastal property listing values given the estimated rise in U.S. coastal sea waters over the next ten years provided by the National Oceanic and Atmoshpheric Administration. 

Unfortunately, the ladder two questions we were unable to analyze given the constraints on our data. First, we could not locate enough accurate and consist median housing prices for inland zip codes at different distances from the coast. This is beacuse the the farther inland zipcodes were no longer comparable to our coastal zip codes as there were several variables, such as median housing price, size, altitude, and demographics, that are too different between the two regions. Therefore, we kept our analysis to looking at inland zip codes that are highly comparable to adjacent coastal zip codes to provide more accurate results. 

Moreover, we were unable to predict coastal property listing values over the next 10 years primarily due to our timing constraint and our overenthusiasm in trying to use our regression to make real world predictions. We ran into multiple problems trying to create our predictions as after we filtered the intial dataset we attempted to reinclude pricing information for later dates through 2021. However, this caused several issues including not predicting prices and having certain zipcodes come up as NaN. With more time we would investigate this problem further to create accurate predictions, but for today we decided to move forward and pivot our prediction to trying to predict prices for inland and coastal homes in our test dataset. While we recognize this prediction does not provide us with real world estimations for future prices, we wanted to test the accuracy of our predicition model to see if it could be used for future housing price predictions once we were able to fix our problem with loading in more current data. 

For our hypothesis, we predicted that a rise in sea level has a statistically significant impact on the listing prices of homes in U.S. coastal cities when compared to home prices in adjacent zip codes. To explore this hypothesis, our null hypothesis is that the median change in coastal city home listing prices associated with a 1 mm rise in global sea levels is equal to 0, or β1 = 0, with all other variables held constant. Our alternative hypothesis therefore tests if this association is not equal to one, or β1 ≠ 0, and if any correlation is present between these variables.

To answer these questions above, we worked as a team to analyze our filtered dataset and create visualizations that accurately display our findings. We are excited to present our analysis methods and findings below:

## Our Data <a name="dataclean"></a>
Info about our data and how we sourced/cleaned it here.

## Methodology <a name="meth"></a>

Here is some code that we used to develop our analysis. Blah Blah. [More details are provided in the Appendix](page2).
 
Note that for the purposes of the website, you have to copy this code into the markdown file and  
put the code inside trip backticks with the keyword `python`.

```python
import seaborn as sns 
iris = sns.load_dataset('iris') 

print(iris.head(),  '\n---')
print(iris.tail(),  '\n---')
print(iris.columns, '\n---')
print("The shape is: ",iris.shape, '\n---')
print("Info:",iris.info(), '\n---') # memory usage, name, dtype, and # of non-null obs (--> # of missing obs) per variable
print(iris.describe(), '\n---') # summary stats, and you can customize the list!
print(iris['species'].value_counts()[:10], '\n---')
print(iris['species'].nunique(), '\n---')
```

Notice that the output does NOT show! **You have to copy in figures and tables from the notebooks.**


## Analysis of Our Findings <a name="section2"></a>
Talk about our overall findings here and include information about our data.

### Price History <a name="subsec2-1"></a>
This is a subsection, formatted in heading 3 style

![](graphs/coastal_inland_price_history.png)
<br><br>
Some analysis here

### Price Distribution <a name="subsec2-2"></a>
This is a subsection, formatted in heading 3 style

![](graphs/price_distribution_coastal_vs_inland.png)
<br><br>
Some analysis here

### Mean Price Coastal vs. Inland <a name="subsec2-3"></a>
This is a subsection, formatted in heading 3 style

![](graphs/mean_price_vs_GMSL_noGIA.png)
<br><br>
Some analysis here

### Price vs Sea Level <a name="subsec2-4"></a>
This is a subsection, formatted in heading 3 style

![](graphs/price_vs_GMSL_noGIA_coastal_inland.png)
<br><br>
Some analysis here

### Correlation Heatmap <a name="subsec2-5"></a>
This is a subsection, formatted in heading 3 style

![](graphs/corr_heatmap.png)
<br><br>
Some analysis here

## Future Predictions <a name="section3"></a>

Here are some graphs that we created in our analysis. We saved them to the `pics/` subfolder and include them via the usual markdown syntax for pictures.

![](pics/plot1.png)
<br><br>
Some analysis here
<br><br>
![](pics/plot2.png)
<br><br>
More analysis here.
<br><br>
![](pics/plot3.png)
<br><br>
More analysis.

## Summary <a name="summary"></a>

Blah blah



## Meet the team

<img src="pics/julio.jpg" alt="Boz" width="300"/>
<br>
The Boz, aka Bos, is a senior at Lehigh studying finance. 
<br><br><br>
<img src="pics/Will.png" alt="Bozymandias" width="300"/>
<br>
Bozymandias, aka Will, is a senior at Lehigh studying finance, real estate, and business information systems <br>
<br><br><br>
<img src="pics/julio.jpg" alt="Bozington" width="300"/>
<br>
Bozington, aka Linh, is a senior at Lehigh studying finance.
<br><br><br>
<img src="pics/editedme.png" alt="Bozzler" width="300"/>
<br>
Bozzler, aka Carter, is a senior at Lehigh studying finance. 


## More 

To view the GitHub repo for this website, click [here](https://github.com/WilliamRoth82/BozandtheBozzers).
