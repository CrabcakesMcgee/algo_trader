# algo_trader

## Required:  
Python3.8  
Jupyter  
Pandas  
Requests  
Researchpy  

## Research Question and Background

Is Volume Weighted Adjusted Price (VWAP) an accurate indicator of stock price?  
Is Exponential Moving Average (EMA) an accurate indicator of stock price?

## Importing Data

Stock prices for SPY were pulled through a TDAmeritrade API. Since an account is necessary to access data, I pulled the data and created the graphs for March 22 - 26. My API key and urls are saved in a config.py file.  
Example of config.py:  
api_key = 'YourAPIKey'  
Mar22 = 'https://api.tdameritrade.com/v1/marketdata/SPY/pricehistory?frequencyType=minute&frequency=1&endDate=1616454000000&startDate=1616400000000&needExtendedHoursData=true'  

## Cleaning Data

Data was cleaned by correcting timezone into something readable, calculating VWAP, and EMA.  
Example:  
Timezone of 1616454000000 was corrected to 23:00:00.  

## Data Visualization

Pulled API data was converted into readable graphs using matplotlib, and then saved by date.  
Example:  graphMar22.png  

## A model
Mean, Standard Deviation, Confidence Interval, t-test, and p-value (among others) were calculated using researchpy.  

## Conclusion

The t value:  
VWAP and AVG was high for each day indicating that these two values are significantly different, meaning one could **NOT** use the VWAP to accurately estimate the current price.  
EMA and AVG was low for each day indicating that these two values are significantly similar, meaning one could use the EMA to accurately estimate the current price.  