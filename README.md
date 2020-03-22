# Covid-19 Analysis and Forecast
#### by Khairul Omar
My analysis and forecast of the Coronavirus pandemic as it happens using daily raw data released by <a href="https://coronavirus.jhu.edu/map.html">John Hopkins University</a>. For details on Python codes used in this report, please refer to the <b><a href="https://nbviewer.jupyter.org/github/khairulomar/Covid-19/blob/master/Covid19.ipynb?flush_cache=true">Covid19.ipynb</a></b> Jupyter notebook. Data on this site will be updated on a daily basis.
<P>
  
## Analysis of actual confirmed cases to date
While China still holds the most number of confirmed cases to date, the centre of the outbreak now concentrates in Europe and the United States while continues to record large number of new cases everyday.   
<p>
<u>Figure 1: Total number of cumulated cases and new daily cases for Top 20 countries</u>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/total_cases_bar.png?raw=true">
<p>
While the total number of cases is a key indicator, it is also critical to analyse the <b>growth factor</b> or the rate at which the total number of cases grow each day. As the growth of a viral outbreak is exponential in nature, an increase of this factor would significantly increase the total cases particularly when a critical mass is reached. A factor close to 1.0 indicates that a plateau is about to be reached.
<p>
<u>Figure 2: Changes in growth factor of key countries since the onset of the outbreak</u>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/growth.png?raw=true">

<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/total_cases.png?raw=true">

  
  
## Forecasting the peak and plateau of outbreak by country
Based on actual cases up to Mar 11, an ARIMA(1,2,1) time series model gives out the following forecast on new cases over the next six weeks:
<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/forecast_uk.png?raw=true" align=left> 
