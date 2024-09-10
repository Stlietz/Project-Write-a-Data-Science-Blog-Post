# Analyzing AirBnB House Prices in Seattle


### Installation and libraries
The entire code should run with Python versions 3.7 or higher
In particular, the following libraries were used:
- numpy
- pandas
- sklearn
- seaborn
- matplotlib.pyplot
- nltk


### Motivation
In the project, the subject of the analysis are house prices in Seattle on AirBnB. Understanding the components of house prices enables consumers to make informed decisions.

In particular, the following questions were investigated
- Which variables correlate with house prices?
- Do Review Scores, Location and Sentiment in the comments explain prices resp. matter?
- When modelling house prices (predicting) using a linear model (Lasso) which are the most important (significant) features and what effect do they have on price - considering all amenities of a house?


### Files:

- listings.csv: main data with various information (variables) describing the listings on AirBnB
- calendar.csv: time series of price and listings, not used in the project (so far)
- reviews.csv: listings with reviews (in textform / strings). Can be joined with listings file on listing id. The review data can be used for sentiment analysis


### Project Summary:
- Especially variables that are a proxy of house size are correlated with prices
- Review Scores do not contribute in explaining house prices. Location and Sentiment in the Review comments on the other hand do

**The bootstrapped Lasso Regression indicates the following**:

*Model Performance*:

Model score of 65.38% of explained variablity on test data indicates that it captures the true underlying relationship to a sufficient extent.


*Frequency of coefficients*:

Only the coefficients which are more likely than not were further investigated, that is, of which the coefficient is nonzero in more than 50% of the cases
In particular, the variables: accomodates, bedrooms, elevator in building, cleaning fee, bathrooms, location cluster 2, and entire house stand out, since they are in each of the 5,0000 bootstrap iterations non-zero.
Moreover, the significance of cleaning_fee, and for example security_deposit are not surprising, since they might be a share of total price
The computed sentiment score appears to be of importance


*Magnitude and sign of coefficients*:

Entire_house, accommodates bedrooms, bathrooms clearly indicate that the size of the house matters the most
The better the sentiment in the comments, the higher the price
You certainly pay for air conditioning
In line with the analysis before: location simply matters! Some regions reduce the average price you pay, some increase it - goes without saying, but is reassuring the coherence of the relationship the model is representing
the coefficient of the "Hangers" is still a conundrum and may point at the limitations of the model
So, if you want to reduce the price you pay, you have a lot of opportunities, e.g. forgo an elevator (esp. if you are on ground floor anyway!), or even search for houses where the sentiment in the comments is not too optimistic, but all other information indicates its a favourable occasion (if you are bold enough). Or simply pass on the buzzer...

### Acknowledgements:

**Udacity** for setting up this awesome project in their [Data Scientist Nanodegree](https://www.udacity.com/course/data-scientist-nanodegree--nd025?promo=year_end&coupon=SKILLS50&utm_source=gsem_brand&utm_medium=ads_r&utm_campaign=19167921312_c_individuals&utm_term=143524475679&utm_keyword=data%20scientist%20udacity_e&utm_source=gsem_brand&utm_medium=ads_r&utm_campaign=19167921312_c_individuals&utm_term=143524475679&utm_keyword=data%20scientist%20udacity_e&gad_source=1&gclid=EAIaIQobChMIlNyctJC_hgMVJ6loCR3eowY6EAAYASAAEgJhzPD_BwE).

