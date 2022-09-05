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

## Modeling

From the data we were able to discern that the market peaked in 2008 and then crashed, so we did not utilize the data prior to the crash as it is a normally stable market which took a crash and this would have greatly effected our model.

After our initial ROI investigation, we determined that Pittsburgh would be the metro we used to train our model and we choose 2012 as the time frame from which we would begin our modeling and utilize those 6 years to forecast our future predictions.

I utilized the SARIMAX model because of the fact that I could use my data without any further cleaning or filtering, the SARIMAX model automatically does differencing and acounts for seasonality.  This means that the model will become stationary without firther changing of the data.

After fitting the model, we were able to run the following diagnostic check to ensure that our model was not correlated and had a normal distribution.

![image](https://user-images.githubusercontent.com/98813858/188423669-f869ce65-e6e2-49b2-9aa3-df60120979d5.png)

In the top right our KDE line closely follows the normal distribution, having a mean of 0 and a std   deviation of 1<br>
Our qq plot closely follows our our residuals line trend line.  <br>This shows us that our residuals are normally distributed
From the Correlogram we can see that the time series residuals have a low correlation with their lag versions and it becomes clearer as we move further along the time series


From these observations, we can assume that there are not obvious correlations and we can fit the model for predictions of future prices

# Recommendations and Conlusions

NOw that we had a model that worked and we could fit it onto our data set to test, we forecasted out Pittsburgh for 3 years

![image](https://user-images.githubusercontent.com/98813858/188433126-5a8c47d3-8c69-4aed-90c3-a8e55271dcbf.png)


Once we had a model which worked on one Metro, we were able to run the model across all of the Metro's that were within our clients set Geographical and budget constraints.

With this we were able to forecast the data out for 3 years and determine the 5 highest ROI within our data set.

![image](https://user-images.githubusercontent.com/98813858/188433888-6e497242-c009-40e1-a6a3-1e3e8318487d.png)

All five of these Metro areas outporformed the mean ROIN for the data by a wide margin and all would be great options for investment, so next we looked at the risk involved and how spread the forecast confidenc interval would be.  The Investment compane wants to ensure that they are not only making a good ROI but that they are also limiting the risk involved with this investment.  We utilized confidence intervals to give us an upper and a lower prediction and then calculated that as a function of the purchasing price to give us an error percentage.

![image](https://user-images.githubusercontent.com/98813858/188434311-516ca758-7658-4664-97e8-1ebd77011845.png)


From the combination of these two sets of forecast information, we are making the recomendation to begin the real estate investment process in Pittsburgh and Reading.  They have a top five projected ROI, but come with a much lower associated risk of investment.  Oil City and Meadville come with an equally high projected ROI but they come with a greater projected risk factor, being that the range of projected selling prices is much wider then our other options.























