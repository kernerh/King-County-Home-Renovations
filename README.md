# King County Home Renovations 
***
Author: Hana Kerner

![King County](KingCounty.png)


## Overview
***
Established in 1976, Sotheby’s International Realty has become the world’s premier luxury residential real estate brokerage. With a global footprint and international network spanning across 74 countries and territories, Sotheby's is most involved in New York, France, Italy, Madrid, Miami, Hong Kong, Bahamas, and Tokyo. Sotheby’s is working to gather a more nuanced understanding of the real estate market in King County, Washington. However, rather than selling new homes, their current interests lie with renovations. They have tasked us with gaining insights as to where they should advise homeowner’s to spend their money, when they are looking to renovate. 

Our goal is to help homeowners decide where they should allocate their time, money, and resources when renovating. Our focus is to provide advice to homeowners on how specific renovations may increase the estimated value of their homes, and what dollar value is attached to this. We are looking to gather insights into the historical housing market trends, to be able to provide homeowners with the best possible recommendations.  

Sotheby's is looking to tackle opportunities in markets where they do not have as strong of a footing. They have asked us to analyze the King County housing market. King County is located in the U.S. state of Washington. In the 2020 census, the population was 2,269,675, making it the most populous county in Washington, and the 13th-most populous in the United States. The county seat is Seattle, which is state's most populous city. 

We have been provided with the King County House Sales dataset, which is where the entirety of our data will come from. Our method parses through this data, and includes cleaning, preparing, visualizing, modeling, interpreting, and presenting the data. We will use data visualization and linear regression modeling to yield findings and support our recommendations. 

The features and trends that we will be forming recommendations around include:
- Square Footage of Living Space 
- Number of Bathrooms 
- Number of Bedrooms 
- Grade of Home
- Condition of Home
***

## Business Problem
***
We are looking to predict the sale price of houses in the King County Housing Market in King County, to create actionable insights for homeowners pertaining to the features of houses that will provide them with the highest financial gain. The homeowners will then be able to use these recommendations when moving forward with where to allocate their time and money with respect to their home renovations. 

**By analyzing raw real estate data and breaking down the trends of the housing market in King County, we will be able to advise homeowners on how increase the value of their property.**

The analysis below aims to answer the following questions:

1. **How does number of bedrooms impact the selling price of a home in King County?**

Understanding how the makeup of a house impacts its price will be crucial in being able to aid homeowners with their renovations and advise them with the most successful strategy to increase the value of their property. It seems likely that the number of bedrooms in a home may be related to its selling price.

2. **How does number of bathrooms impact the selling price of a home in King County?**

The same holds true here. Our expectation is that the more bathrooms a home has, the higher its selling price will be, but, by how much? Is this significant?

3. **How does grade impact the selling price of a home in King County?**

Grade can vary a lot in respect to a home, and in respect to how a home is being graded. Will we see consistency in the data? Does the grade of a home, from one rating to the next, impact the selling price? What is the makeup of this category, and how can we help homeowners implement it?

4. **How does condition impact the selling price of a home in King County?**
We believe that the condition of a home would be positively correlated to selling price, and are hoping to find out if this is a strong predictor for that price. If so, this may be a very feasible area for homeowners to make improvements, if it comes down to small repairs and adjustments to keep their home up to date.
***

These questions are crucial in deciding how we will advise homeowners to move forward, as we will have a better understanding of housing characteristics, and thus, an understanding of what homeowners should focus on to see the greatest possible returns.
***

## The Data
***
The data used for this project is from the King County Dataset. This is a dataset of real-estate data from King County, Washington. The dataframe is `kc_house_data`. This dataframe consists of 2,1597 rows and 21 columns. We will be cleaning and adjusting our data quite a bit, and ultimately, 'price', and a new variable that we will call `price_log`, will be the target variable. Each entry in this dataset represents a house sold in King County. Our most relevant columns will be:

* `sqft_living` (and it's altered forms)
* `bedrooms` (and it's altered forms)
* `bathrooms` (and it's altered forms)
* `grade` (and it's altered forms)
* `condition` (and it's altered forms)
* `price` (and it's altered forms)

Our data process will consist of multiple steps. Ultimately, we will be conducting statistical analyses and developing a Linear Regression model to predict the sale price of a King County house. These predictions will allow us to have concrete numbers and values to help homeowners make informed decisions when faced with renovations. 

Our data process will consist of:
***
- Importing and processing the data 
- Cleaning the data (handling missing values, datatypes, duplicates, etc.)
- Describing the data and relationships we may see 
- Transforming variables 
- Fitting models
- Gathering insights and interpreting findings 
- Developing conclusions and recommendations 
***

## Methods
***
Our data process will consist of multiple steps. Ultimately, we will be conducting statistical analyses and developing a Linear Regression model to predict the sale price of a King County house. The coefficients from this model will be used to find the precise dollar amounts for different features. These predictions will allow us to have concrete numbers and values to help homeowners make informed decisions when faced with renovations. 

Our data process will consist of:
***
- Importing and processing the data 
- Cleaning the data (handling missing values, datatypes, duplicates, etc.)
- Describing the data and relationships we may see
- Handling categorical variables 
- Transforming variables
- Scaling data 
- Handling Multicollinearity
- Fitting models
- Checking linear regression assumptions 
- Gathering insights and interpreting findings 
- Developing conclusions and recommendations 
***

## Modeling 
***
Here, we will go through multiple iterations testing our different features against our response variable, and seeing what our `r-squared` value is. This will be our main measure of predictive performance. We will look at multiple metrics throughout this process. 

We will use OLS regression and to determine the success of our model by using: 

`R-squared`: Value communicating how much of the variability of our dependent variable (price) can be explained by the model <br>
`Adjusted R-squared`: Considers and tests different independent variables against the model. Our r-squared value does not do this, so if we see a difference between the two, we will use the adjusted r-squared<br>
`Null hypothesis`: Our null hypothesis for these models is that there is not a relationship between price and any chosen variable<br>
`Alpha`: Our alpha value will be .05<br>
`P-value`: This is our metric in checking the null hypothesis, and determining the validity of our models predictors. If our p-value is below our alpha of .05, we can reject our null hypothesis<br>
`Coefficients`: These are values we can use to explain teh relationship between our predictors and our outcome variable <br>
***

## Results
***
Our final model is over the goal we set out of having an `r-squared` value of over 60%. Right now, our `adjusted r-squared` stands at **0.622**. This tells us at 62.2% of the variations in price *y* are explained by the features in our model.

We also can be satisfied with our `p-values`, that are all lower than our alpha of .05. This tells us that our features are statistically significant in relation to the variance of our dependent variable, which is price. 

## Conclusions
***
We have multiple insights that we will be able to share with the Sotheby's team based on our analyses.

Our original questions that we posed revolved around square footage, bedrooms, bathrooms, grade, and condition of a home. To our team, these are all areas that seem to be relevant when considering a renovation, and have the potential to increase the value of a home. After a rigorous modeling process, we have some answers. 

**Square Footage**: 
When it comes to renovating a home, focusing on the square footage of living space in the home matters. We found that for every 1% increase in square footage, there is a .27% increase in price. In other words, for every 20% increase in square footage, our price increases by about 5%. To put this into dollars, according to *Redfin* and *Rocket Homes*, **the median price of a home in King County as of September 2022 is about 815,000 dollars.** Using this as a baseline, our model tells us that if we increased our square footage by 20 percent, the value of our home would increase to $855,750. This is a **40,750 dollar** increase! 

**Bedrooms**: 
Unfortunately, our model did not provide us with convincing data on how increasing the number of bedrooms in a home would increase the value of a home. We will discuss this more in **next steps**, discussing how we can learn more about this in the future. That being said, after analyzing the distribution, we do know that while the majority of homes in King County have 3-4 bedrooms, **over 75 percent of the most expensive homes in King County have 4-5 bedrooms.** This is helpful, as we were visually able to see the impact of this jump in bedroom count.

**Bathrooms**: 
Looking at our distributions, we saw that the majority of homes in King County have between 1-2.5 bathrooms, but the majority of the most expensive homes in King County have between 3-4.5 bathrooms. As we look at the trend of our data, it is clear that as the number of bathrooms in a home increases, the price of the home increases. Every single one of our dummy variables with price is positive. From this, we can understand that the addition of each new bathroom in a home increases the value of the home by a positive percentage. For example, having 4 bathrooms adds 31.49 percent to our sale price, where having 1.75 bathrooms adds 8.42 percent to our sale price. 

**Grade**: 
We saw from the beginning that grade is one of the biggest predictors of price. This was a great finding for us, as often, renovations revolve around grade improvements. Our model shows that having a grade **above 9** adds value to our home. When our home reaches a grade status of 11, 12, and 13, we significant increases to our sale price. This tells us that this may be the prime feature to focus on with home renovations, where our homeowners are likely to reap the rewards of their investments. This is what they should aim for:

*Grade 11: Custom design and higher quality finish work with added amenities of solid woods, bathroom fixtures and more luxurious options.*

*Grade 12: Custom design and excellent builders. All materials are of the highest quality and all conveniences are present.* 

*Grade 13: Generally custom designed and built. Mansion level. Large amount of highest quality cabinet work, wood trim, marble, entry ways etc*  

In short, achieving a home categorized as Grade 11 Luxury increases the value of a home by 37.5 percent. Using our same basline from our square footage calculations, this could mean **increasing the price of a home from 815,000 dollars to 1,120,625 dollars.** This is a 305,625 dollar increase!

**Condition**: 
Similar to grade, we see that condition has a large impact on selling price. Having a Fair Condition has a negative impact on our price, while having a Good or Very Good condition increases the value of our home. Again, this is unsurprising. We suggest that our homeowners aim for the following condition standards:

*4 - Good. No obvious maintenance required but neither is everything new. Appearance and utility are above the standard and the overall effective age will be lower than the typical property.*

*5 - Very Good. All items well maintained, many having been overhauled and repaired as they have shown signs of wear, increasing the life expectancy and lowering the effective age with little deterioration or obsolescence evident with a high degree of utility.*

Our model tells us that **having a home categorized as Fair decreases the value of a home by about 14.73 percent, but having a home categorized as Good increases its value by about 19.39 percent.** Again, in today's market **this variation accounts for a home price that can range from 694,950.50 - 973,028.50 dollars. That is a 278,078 dollar difference!
*** 

## Next Steps 
***
As confident as we are in our recommendations, there is a lot of nuance to our model and we know small changes can be a big difference. Going forward, these would be our areas of focus: 

1. Look into location - we did not analyze our zipcode or latitude and longitude data. We know the age old saying: 'Location, Location, Location.' In other words, identical homes can increase or decrease in value due to location. We want to help homeowners with how best to renovate their homes, but maybe in one part of King County, adding a bathroom detracts from the sale price, while in another area, adding a bathroom doubles the sale price? These are patterns we can begin to analyze with location data.

2. Our data is outdated, only extending to the year 2015, and only including data from 2014 and 2015. We were able to complete our analysis with this data, but further work would definitely include extending this to the current real estate climate, as we know how fickle the housing market can be.

3. A large part of our emphasis has been on improving the condition and grade of a home. But, how can we now help homeowners with the specifics of that? For condition, we can look deeper into the best ways to maintain a home, at the lowest cost to our homeowners. For grade, we can look into solid woods, bathroom fixtures, cabinet work, wood trim, marble, and entry ways, and see which of these characteristics increase selling price the most, and advise our homeowners to allocate their money in that direction.

4. Although we have seen what characteristics of renovation may be useful, we have not tracked this in relation to the cost of each renovation. This is somewhere we could direct our energy in the future. If we find that the return of time and money on adding a bathroom is far less than that of adding marble and wood trim to a home, maybe that is where we suggest our homeowners allocate their resources. 
***

## For More Information
***
Please review our full analysis in our Jupyter Notebook or our presentation.

For any additional questions, please contact Hana Kerner at haych20@gmail.com
***

## Repository Structure
***
├── images                              <- Both sourced externally and generated from code
├── data                                <- Both sourced externally and generated from code
├── README.md                           <- The top-level README for reviewers of this project
├── final_notebook.ipynb                <- Narrative documentation of analysis in Jupyter notebook
└── presentation.pdf                    <- PDF version of project presentation

