## DSCI 532 Group 212 Proposal: Social Mobility Project

### Section 1: Motivation and Purpose

In an ideal world, every child would have the opportunity to achieve success regardless of what social class they happened to be born into. 
Having a low potential for socio-economic mobility means that a child's ultimate life prospects are more or less predetermined by the education or income level of their parents, whereas a high mobility is an indication of an equal-opportunity society.  Research has shown that higher social mobility also leads to increased economic growth and social stability (Source: [GDIM, 2018](https://openknowledge.worldbank.org/bitstream/handle/10986/28428/9781464812101.pdf)).  We feel that this makes it a better metric for measuring societal success over other traditional factors such as GDP.
We are proposing to build a visualization app that uses educational mobility as a proxy for overall socio-economic mobility to show how it has changed globally over the last four generations. 

### Section 2: Description of the data

The dataset we are using was compiled by the World Bank, and includes estimates of "absolute and relative intergenerational mobility (IGM) by 10-year cohorts, covering individuals born between 1940 and 1989" (Source: [GDIM, 2018](http://pubdocs.worldbank.org/en/734501527703249115/GDIM-Description-May29.pdf)).  We are going to be focusing on the education mobility data which covers 148 countries for at least one generation, and 111 countries over multiple generations.

The main variable we are plotting in all our visualizations is educational mobility. The raw dataset includes a column named `IGP` which represents intergenerational persistance in education. This is calculated from drawing a regression line between a child's years of schooling (or highest education level) and the highest education level of their parents.  The `IGP` s calculated in a way that higher values mean less mobility and lower values mean more mobility. This takes more cognitive effort when looking at plots, so for our visualiztion purposes we have made a new variable called `ed_mob_index` that maps the best World Bank `IGP` to a value of 1 and the worst to a value of 0. We feel that using this index makes the plots easier to follow (higher index = improved mobility!).

 We also use the following variables to allow the user to make selections for comparisons:
 - `countryname`: name of the country
 - `region`: continent name
 - `incgroup2`: either high-income economies or developing economies
 - `incgroup4`: this further splits developing economies into 3 subcategories: low, middle, and high.
 - `year`: this is the decade children are born in. Options are 1940, 1950, 1960, 1970, or 1980. 
 - `child`: either son or daughter

 There are many other columns in the raw dataset that we will not be including in our visualizations. Many of these are indicators or coefficients that are used to calculate the `IGP` and another mobility index relating to economic mobility, `IGE`.  For the purposes of this dashboard, we are excluding data relating to economic mobility since there is very little data available compared to educational mobility. We also take the `IGP` as a starting point instead of re-calculating all the estimation parameters.  A detailed description of each of these columns can also be found [here](http://pubdocs.worldbank.org/en/734501527703249115/GDIM-Description-May29.pdf).
 

### Section 3: Research questions and usage scenarios

Professor Moriarty, a reputable Sociology professor at UBC, is exploring different ways to make his class’s term paper more engaging. The Teaching Assistant (TA) assigned with this endeavour, was coincidentally also the TA for MDS. The TA decided to use an app created by MDS students which enables one to visualise trends in the education index globally. The app would provide the sociology students with ample oppurtunity to look further into trends in education opportunity across the globe for their term paper. 

When using the app Tanvi, a Sociology major, will land on an interactive map of the world encompassing the education index for all given geographies across four generations. The app enables her to visualise a comprehensive global database collected on intergenerational mobility using education index as a proxy for overall class mobility/equality. By hovering over a region, she can get the education index for a chosen generation for any country. A histogram on the right will further aid her insight by providing the global rank of this country for the chosen generation. The histogram also includes color encoding to allow her to identify whether the country is deemed a developing economy or a high-income economy. 

For example, if she chooses the 1940 generation (representing people born in the 1940's), she might observe that South Africa has the highest education index amongst all African countries. In fact, if she expands her view along the map, she will also see that it is on par with the developed economies of the time. This could lead her to choose South Africa as her country of interest and then formulate a deeper insight into South Africa’s progress over generations and compare it to other countries. 

The bottom half of the dashboard would enable her to perform this task using a more granular approach. From the drop down menu, she can choose to compare South Africa with any other country or region of her choosing, say USA. The three plots on the bottom would allow her to explore the following questions:
- How has the overall education opportunity changed for South Africa compared to the USA over time?
- Are the changes different for men and women?
For example, she might notice that in South Africa, the education index fell for the first three generations and then displayed minor improvements. On the other hand, it rose consistently in the US.
However she might also find that the education index of women, though historically disadvantaged, has shown an upward trend in the last generation for both countries. 

With this information in hand, she decides to write her paper on the impact of woman’s education on the upward mobility of a generation as a whole. In future, she can further build upon this by combining this visualization app with the Gap Minder dataset, to investigate the correlation between a country’s average per capita GDP and its maternal education index.

## Description of your app & sketch 

The app will feature a global map that will allow users to get a big-picture view for a selected generation along with the ability to get specific information for any country. There is a bar chart next to the plot showing the overall ranking of all countries for the selected generation.  Below the map, the app will include three interactive plots where the user can select two countries or regions to compare against each other more closely in terms of overall education index, education index for men and women, and overall ranking.  

![](img/Dashboard_Schematic.jpg)




