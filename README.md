# Forecasting the peak and plateau phases of Covid-19 outbreak
<b>by Khairul Omar</b><br>
<a href="https://www.linkedin.com/in/khairulomar/">linkedin.com/in/khairulomar</a><br>
khairul.omar@gmail.com
<p>
My analysis and forecast on the Coronavirus pandemic as it happens using daily raw data released by <a href="https://coronavirus.jhu.edu/map.html">John Hopkins University</a> is presented here. Data on this site will be updated on a <b>daily basis</b>.
<p>
For details on Python codes to derive the analysis and forecast, please refer to <b><a href="https://nbviewer.jupyter.org/github/khairulomar/Covid-19/blob/master/Covid19.ipynb?flush_cache=true">Covid19.ipynb</a></b> Jupyter notebook.
<p>
<img align="left" width="75" height="75" src="https://github.com/khairulomar/Covid-19/blob/master/img/disclaimer.png?raw=true"><b>Disclaimer: Please interpret the model results with caution and refer to the respective countries' government agencies and the World Health Organization (WHO) as the leading authorities on the subject matter and for the official forecasts.</b><p>
  
## Analysis of actual confirmed cases to date
Despite China being the initial epicentre of the crisis, the outbreak now concentrates in Europe and the United States which continue to record large number of new cases everyday.
<p>
<b>Figure 1: Latest number of cumulated cases and new daily cases for Top 20 countries</b>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/total_cases_bar.png?raw=true">
<p>
While the total number of cases is a key indicator, it is also critical to analyse the <b>growth factor</b> or the rate at which the total number of cases increases each day. A factor close to 1.0 that remains unchanged for some days indicates that a plateau is about to be reached where the number of new cases would be relatively small.
<p>
<b>Figure 2: Changes in growth factor of key countries for the past 28 days. Value shown is the latest growth factor.</b><br>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/growth.png?raw=true"><br>
Social distancing matters because it reduces the exponential growth, shown above as how many days it’d take for cases to double. We shall see next that countries which still have a high growth rate is projected to continue to have large number of new cases thar is set to overtake China. We can also demonstrate below on how the total number of cases would continue to multiply if the latest growth rates do not start to subside.
<p>
<b>Figure 3: Total actual and 5-day projected number of cumulated cases for key countries</b>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/total_cases.png?raw=true">
  
## Basis of forecasting model
As China and South Korea are the only two countries that are heading towards a plateau in the outbreak, we can look on how the total number of cases evolved from the start until the number of cases stabilises. Although both countries have a fairly similar pattern as shown in the normalized plot below, the shape of the curvature and its timing differs - which required tailored model parameters for each country to be forecasted.
<p>
<b>Figure 4: Comparing how the number of cases reached a plateau in China versus South Korea</b>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/china_korea.png?raw=true">
<p>
The <b>general logistic function</b> (or <b><a href="https://en.wikipedia.org/wiki/Generalised_logistic_function">Richard's curve</a></b>) is chosen as the basis of the forecasting model due to its resemblance to the life cycle of the outbreak.
<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/richards_curve.PNG?raw=true">
<p>
Actual data to date is fit to this curve whereby the parameters used in the equation is fine-tuned using <a href="https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.curve_fit.html"><b>SciPy</b></a> package in Python via least squares method. Below are the results when the optimized model is applied to data for China and South Korea to compare how it performs versus actual cases to date and the reasonable forecast to be expected. For the purpose of this model, it is assumed that re-infection is very unlikely and a second peak of outbreak does not occur.
<p>
<b>Figure 5: Model fit results for China and South Korea</b>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_China.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_South_Korea.png?raw=true">
  
## Forecast for key countries
Using the technique applied and tested for China and South Korea, the model is rolled out to other key countries in order to identify the possible timing of two key milestones:
1. The turning point when the number of new cases would start to drop 
2. The amount of time remaining before the total number of cases would stabilize due to very small number of new cases. This should not be strictly interpreted as the end of outbreak or the lockdown measures for a given country as there are other factors at play.
<p>
Note that the forecast for some countries below may not be shown to extended points in time as the Python package fails to reach a convergence point after thousands of iterations, mainly due to the limited available periods and a very high rate of change of growth that does not fit Richard's curve beyond a certain range of data points.
<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_United_Kingdom.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Italy.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_United_States.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Spain.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Germany.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_France.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Switzerland.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Iran.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Malaysia.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Australia.png?raw=true">
