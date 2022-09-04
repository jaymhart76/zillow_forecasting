# Zillow - Time series forecasting Model

## Business Case and Project focus
We will be presenting this case to a real estate investment firm from Princeton, that is looking for us to analyze the data and determine what Metro area is best for their investment and this analysis will give them the ability to narrow down their focus and determine where to look for investments.

We will be using the Zillow dataset which covers the years from 2000-2018 and we will be focused in the Northeast, our client has determined that the area of business for them is the states within a reasonable drive from their home office in Princeton, NJ.  We will filter the dataset to only contain the east coast homes from Delaware, Pennsylvania and New Jersey.  This will give them information on what the forecasted growth for these markets would be and where they should focus their attention and their greatest opportunities will be.

Our client also only wants to start with an investment of $250,000 per home since they will be looking for multiple homes to invest in, so we will have to filter the data set to eliminate the more expensive homes.

## Data set Utilized
The data set encompusess the sales data for over 

There are 14,723 rows and 272 variables:

..* RegionID: Unique index, 58196 through 753844
* RegionName: Unique Zip Code, 1001 through 99901
* City: City in which the zip code is located
* State: State in which the zip code is located
* Metro: Metropolitan Area in which the zip code is located
* CountyName: County in which the zip code is located
* SizeRank: Numerical rank of size of zip code, ranked 1 through 14723 1996-04 through 2018-04: refers to the median housing sales values for April 1996 through April 2018, that is 265 data points of monthly data for each zip code


## Data Filtering

* Imported and read into a Pandas DF
* There are 14,723 rows and 272 variables:

    *RegionID: Unique index, 58196 through 753844
    *RegionName: Unique Zip Code, 1001 through 99901
    *City: City in which the zip code is located
    *State: State in which the zip code is located
    *Metro: Metropolitan Area in which the zip code is located
    *CountyName: County in which the zip code is located
    *SizeRank: Numerical rank of size of zip code, ranked 1 through 14723 1996-04 through 2018-04: refers to the median housing sales values for April 1996       through April 2018, that is 265 data points of monthly data for each zip code

