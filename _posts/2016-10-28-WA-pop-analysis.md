---
title: Analyzing the population growth in Washington State from 1990 to 2016 using R
updated: 2016-10-28
---
header: 
image: ![mypic](https://cdn-images-1.medium.com/max/1000/1*eIITiGw7fpg8dQ5K0Bcf2A.jpeg)
caption: "Photo Credits: Avinash Kamath"

This post was riginally posted in [medium](https://medium.com/@avi.k?source=post_header_lockup)

After moving to the greater Seattle area this summer, I have been exploring the pacific northwest a lot. I heard a lot about the exploding prices of homes and rental properties and how comparable Seattle has become to the Bay Area. With major tech companies such as Microsoft, Amazon and several startups having Greater Seattle Area as their base, this growth didn’t seem that surprising to anyone who spoke about it. While I agree this has to be true, I wondered how this growth was spread out around Puget Sound area, over time. I kept thinking about how the population growth around Seattle must have spilled over leading to eventual growth in neighboring areas. Therefore, I decided to analyze and decipher population growth and its pattern across Washington State.

For this analysis, I have used the 1990–2016 county wise population dataset available in the open data portal for Washington state (Click [here](http://data.wa.gov/Demographics/WAOFM-April-1-Population-by-State-County-and-City-/tecv-qzfm) to view the dataset). _This dataset did not have location coordinates of the cities. They were derived using Google APIs._  I crunched this dataset using R to plot the year-wise and city-wise growth in population and I have also built an interactive visualization (Click [here](http://nashavi.shinyapps.io/WA_State-Population_Growth/)) using Shiny app framework.

![screenshot](https://cdn-images-1.medium.com/max/1750/0*0auJjiHZQO6qfEWb.png)

Washington is the 13th most populous state in US with over 7 million people. Around 60% of these residents live in the Seattle Metropolitan area which encompasses three counties — King, Snohomish and Pierce. As of 2016, the state has witnessed a 47.61% growth from its population in 1990 and a 22% growth from that of 2000. I will refer to the counties in Washington State quite a lot and the below map from US Census Bureau can be a quick reference for them.

![wacounties](http://www.fluoridealert.org/wp-content/pesticides/levels/map.wa.gif)

As the first step, I identified the trends in increase in residents for every major city in the Washington state, by its county. Here are the relative trends for cities in each of Washington’s counties.

![growthplot](https://cdn-images-1.medium.com/max/1000/0*ctmuVpvauHysutiE.png)


### Now lets consider the highlights of that plot:

- Much of the population increase in the state between 1990 to 2016 is driven by several cities from King, Snohomish and Pierce county

- King county, as expected leads the population growth which is evident from its largest range in Y axis. The purple line in King County is indicative of Seattle population that has increased by over 150,000 during the period.

- Multiple cities in Snohomish county has growth spurts around the year 2005 and a bigger spurt for few others cities around 2010.

- Clark county, closest neighbor to the city Portland in Oregon State, encompasses areas whose population has abnormally spiked sometime between 1995–2000. They have grown by over 100,000 during the overall 26 year period.

- Benton, Franklin, Yakima and Spokane Counties each have at least one city whose population has spanned quite close to 50,000 making them comparable to growth in some of the metropolitan cities in Greater Seattle area.

As the next step, I plotted the city-wise data to understand these trends better on the map of Washington state. I produced a [leaflet](http://rstudio.github.io/leaflet/) map with markings to indicate both the population growth rate as well as the absolute increase in population for this analysis. The results are shown below.

- Size of circle is indicative of the increase in city residents from 1990, and

- Color is indicative of population growth in percentages from the base year 1990 as per the legend.


![finaloutput](https://cdn-images-1.medium.com/max/1000/0*DpwB_DY0AB3SgCK9.png)

**[Click here to view the population growth as an animated graph](http://nashavi.shinyapps.io/WA_State-Population_Growth/)**

_Use the ‘play’ icon to see the animation. You can zoom into any part of Washington state and move the slider manually to see the year-wise growth._


### Analysis of Washington state population growth:

The period 1990–2000 is characterized by instances of growth in north of Seattle towards the Everett side encompassing parts of Snohomish County as well as south of Seattle in Kent, part of King County. During this period, both of these surrounding areas had more than doubled their population. Marysville and Everett areas of Snohomish County also benefitted from the [Naval Station](http://en.wikipedia.org/wiki/Naval_Station_Everett) establishment in 1994. However by 2005, the development around the eastern side of Seattle swayed the population growth away from Snohomish County areas towards — Redmond, Bellevue and Renton. From year 2010, there was another shift of population towards Bothell, Marysville and Mill Creek of Snohomish County. The reason could be the higher housing prices in Seattle or the Eastside. Either way, by 2015, Snohomish County cities were the [fastest growing](http://www.heraldnet.com/news/snohomish-county-leads-all-others-in-population-growth/) areas in Washington state.

Interestingly, the first noticeable big growth during this period happened far away from Seattle, all way to the southern part of the state, in Vancouver, Clark County. Between 1990 and 2000, the population here had tripled. The reason for this can be directly attributed to border economics and proximity to City of Portland in the neighboring state of Oregon. In 1997, a downtown [revitalization program](http://en.wikipedia.org/wiki/Vancouver,_Washington#Downtown_revitalization) was also kicked off by the city leading to further development. By around 2005, this growth had spilled over to the neighboring areas around Vancouver.

Population in Pierce county has been gradually increasing without any spikes or spurts. Most of Pierce county’s population growth is attributable to the northern areas closer to King County and areas around Tacoma. An interesting find from Pierce County is the City of DuPont which had only 592 resident as of 1990 but had increased by over 15 times in the 26 year period. A quick search reveals that the growth spurt started in the year 1997, when [Northwest Landing](http://community.seattletimes.nwsource.com/archive/?date=19980411&slug=2744505), a master planned community, was developed. In the years that followed, [DuPont](http://www.youtube.com/watch?v=jCbkvspdaI4) witnessed double digit growth and by 2016, its population had crossed 9,000.


### Conclusion:

This analysis helped me understand and visualize the basic growth pattern across Washington state. I can infer that the growth percentage analysis indicates ‘hot’ areas for property investment, due to availability of land for new home or rental property construction.

There is much more one can analyze and drill into with this raw dataset. I will save that for another day.

All the R code I wrote to generate the plots and map above are available in [my github account](http://github.com/Nashavi/WA_Pop_Analysis)

