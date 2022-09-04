# Zillow - Time series forecasting Model

## Business Case and Project focus
We will be presenting this case to a real estate investment firm from Princeton, that is looking for us to analyze the data and determine what Metro area is best for their investment and this analysis will give them the ability to narrow down their focus and determine where to look for investments.

We will be using the Zillow dataset which covers the years from 2000-2018 and we will be focused in the Northeast, our client has determined that the area of business for them is the states within a reasonable drive from their home office in Princeton, NJ.  We will filter the dataset to only contain the east coast homes from Delaware, Pennsylvania and New Jersey.  This will give them information on what the forecasted growth for these markets would be and where they should focus their attention and their greatest opportunities will be.

Our client also only wants to start with an investment of $250,000 per home since they will be looking for multiple homes to invest in, so we will have to filter the data set to eliminate the more expensive homes.

## Data set Utilized
The data set encompusess the sales data for over 

There are 14,723 rows and 272 variables:

* RegionID: Unique index, 58196 through 753844
* RegionName: Unique Zip Code, 1001 through 99901
* City: City in which the zip code is located
* State: State in which the zip code is located
* Metro: Metropolitan Area in which the zip code is located
* CountyName: County in which the zip code is located
* SizeRank: Numerical rank of size of zip code, ranked 1 through 14723 1996-04 through 2018-04: refers to the median housing sales values for April 1996 through April 2018, that is 265 data points of monthly data for each zip code


## Data Filtering

* Imported and read into a Pandas DF
* There are 14,723 rows and 272 variables:

    *RegionID: Unique index, 58196 through 753844<br>
    *RegionName: Unique Zip Code, 1001 through 99901<br>
    *City: City in which the zip code is located<br>
    *State: State in which the zip code is located<br>
    *Metro: Metropolitan Area in which the zip code is located<br>
    *CountyName: County in which the zip code is located<br>
    *SizeRank: Numerical rank of size of zip code, ranked 1 through 14723 1996-04 through 2018-04: refers to the median housing sales values for April 1996       through April 2018, that is 265 data points of monthly data for each zip code<br>
* Data was then filtered to contain only the States and mean home prices to fit within budget 
* Data melted to move the dates into the index column


## Data Exploration before modeling


Looked at the information per state for the entire dataset and where there were issues and what the overall shape of the data was<br>

Determined from the data that there was a market crash in 2008 and that the data settled down in 2012
![image](https://user-images.githubusercontent.com/98813858/188322068-07e6722c-3512-4c79-a3a5-bb35dbca9e11.png)

Created a ROI column and looked at what the historical ROI over the entire dataset would return for the Metro areas we were looking at the ROI from 2012-2018

![image](https://user-images.githubusercontent.com/98813858/188322241-6db913ff-1a0b-4784-b707-76400428ef57.png)






