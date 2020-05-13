# Forecasting the peak and plateau phases of Covid-19
<b>by Khairul Omar</b><br>
<a href="https://www.linkedin.com/in/khairulomar/">linkedin.com/in/khairulomar</a><br>
khairul.omar@gmail.com
<p>
My analysis and forecast on the Coronavirus pandemic as it happens using daily raw data released by <a href="https://coronavirus.jhu.edu/map.html">John Hopkins University</a> is presented here. Data on this site will be updated on a <b>daily basis</b>.
<p>
For details on Python codes used to derive the analysis and forecast, please refer to <b><a href="https://nbviewer.jupyter.org/github/khairulomar/Covid-19/blob/master/Covid19.ipynb?flush_cache=true">Covid19.ipynb</a></b> Jupyter notebook.
<p>
<img align="left" width="75" height="75" src="https://github.com/khairulomar/Covid-19/blob/master/img/disclaimer.png?raw=true"><b>Disclaimer: Please interpret the model results with caution and refer to the respective countries' government agencies and the World Health Organization (WHO) as the leading authorities on the subject matter and for the official forecasts.</b><p>
  
## Analysis of actual confirmed cases to date
Despite China being the initial epicentre of the crisis, the outbreak now concentrates in Europe and the United States which continue to record large number of new cases everyday.
<p>
<b>Figure 1: Latest number of cumulated cases and new daily cases for Top 20 countries</b>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/total_cases_bar.png?raw=true">
<p>
While the total number of cases is a key indicator, it is critical to analyse the <b>growth factor</b> or the rate at which the total number of cases multiplies each day. A factor close to 1.0 that remains unchanged for some days indicates that a plateau is about to be reached where the number of new cases would be relatively small.
<p>
<b>Figure 2: Changes in growth factor of key countries for the past 8 weeks.</b><br>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/growth.png?raw=true"><br>
Social distancing matters because it reduces the exponential growth, shown above as the number of days it’d take for cases to double. We shall see next that countries which still have a high growth rate are projected to continue to have a large number of new cases that are set to overtake China. We can also demonstrate below how the total number of cases would continue to multiply if the latest growth rates do not start to subside.

## Basis of forecasting model
As China and South Korea are the only two countries that are heading towards a plateau in the outbreak, we can look on how the total number of cases evolved from the start until the number of cases stabilises. Although both countries have a fairly similar pattern as shown in the normalized plot below, the shape of the curvature and its timing differs - which required tailored model parameters for each country to be forecasted.
<p>
<b>Figure 3: Comparing how the number of cases reached a plateau in China versus South Korea</b>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/china_korea.png?raw=true">
<p>
The <b>general logistic function</b> (or <b><a href="https://en.wikipedia.org/wiki/Generalised_logistic_function">Richard's curve</a></b>) is chosen as the basis of the forecasting model due to its resemblance to the life cycle of the outbreak.
<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/richards_curve.PNG?raw=true">
<p>
Actual data to date is fit to this curve whereby the parameters used in the equation is fine-tuned using <a href="https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.curve_fit.html"><b>SciPy</b></a> package in Python via least squares method. Below are the results when the optimized model is applied to data for China and South Korea to compare how it performs versus actual cases to date and the reasonable forecast to be expected. For the purpose of this model, it is assumed that re-infection is very unlikely and a second peak of outbreak does not occur.
<p>
<b>Figure 4: Model fit results for China and South Korea</b>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_China_latest.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_South_Korea_latest.png?raw=true">
  
## Forecast for key countries
Using the technique applied and tested for China and South Korea, the model is rolled out to other key countries in order to identify the possible timing of two key milestones:

1. The turning point when the number of new cases would start to drop 

2. The amount of time remaining before the total number of cases would stabilize due to very small number of new cases. This should not be strictly interpreted as the end of outbreak or the lockdown measures for a given country as there are other factors at play.
<p>
The model performs better when the growth factor of the cumulative number of cases starts to show signs of a slowdown. When the number of cases continues to grow exponentially at a high rate however, the projected trajectory would be less reliable until more data points are available. Governments all over the world are exercising a similar caution when releasing their own expectations, which makes running a forecast beyond a week or two very difficult when cases are still growing exponentially. For this reason, forecasts by country below are shown with different versions to show how forecasts have changed as new information is available.
<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Spain.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Italy.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_France.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_United_Kingdom.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Germany.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_United_States.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Turkey.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Iran.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Belgium.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Switzerland.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Sweden.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Malaysia.png?raw=true">
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_Australia.png?raw=true">
<p>
Using forecasts tailored by country above, we can make a comparison between different countries to see how the number cases has changed over the past one month and how it is forecasted to change over the next one month as shown in the two charts below.
<p>
<b>Figure 5: One-month forward forecasts for key countries</b>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_multicountries_total_cumulated_cases.png">
<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/forecast_multicountries_daily_new_cases.png">
  
## My publications on Covid-19 analysis

<a href="https://www.ydlmalaysia.com/">Young Digital Leaders</a> (YDL) is an initiative started by <a href="https://twitter.com/DhesiMD">Dr Dhesi Raja</a> and <a href="https://twitter.com/DrAnwarFazal">Dr Anwar Fazal</a>, with the aim to solve global challenges (in health, environment, etc.) through utilisation of data. Data is constantly emerging and evolving, which complicate efforts to properly implement them without rapid and high quality analysis. In addressing the need to bridge traditional methods of solutions to modern-day analytics, data availability, sharing, access and analysis are vital to provide evidence for policy and decision making in both government and private setting. With a dynamic team of data scientists, statisticians, mathematicians, engineers and epidemiologists, YDL is driven to provide insight into current issues in Malaysia and at a global level – by sharing information through analyses, projections and modelling.

<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/ydl-logo-horiz.png?raw=true">                                         <p>                                                             
In partnership with Young Digital Leaders, I authored the following analysis to support decision-makers in tackling Covid-19 outbreak in the country:
<p>
Article 1 : <b>The Impact of Covid-19 Lockdown by Key Countries</b><br>
[<a href="https://github.com/khairulomar/Covid-19/blob/master/malaysia/Malaysia_lockdown.md">My Github</a>] 
[<a href="https://www.ydlmalaysia.com/the-impact-of-covid-19-lockdown-by-key-countries/">YDL Publication</a>] 
[<a href="https://twitter.com/smc_my/status/1246770114134822918">SMCM Publication</a>] 
<p>
Article 2 : <b>Benchmarking Government Response On Covid-19 in Malaysia vs. Key Countries</b><br>
[<a href="https://github.com/khairulomar/Covid-19/blob/master/malaysia/Malaysia_rank.md">My Github</a>] 
[<a href="https://www.ydlmalaysia.com/benchmarking-government-response-on-covid-19-in-malaysia-vs-key-countries/">YDL Publication</a>]
<p>
Article 3 : <b>Evaluating the Reliability of the Number of Confirmed Covid-19 Cases Reported by Various Countries</b><br>
[<a href="https://github.com/khairulomar/Covid-19/blob/master/malaysia/Malaysia_positive_estimate.md">My Github</a>] 
[<a href="https://www.ydlmalaysia.com/evaluating-the-reliability-of-the-number-of-confirmed-covid-19-cases-reported-by-various-countries/">YDL Publication</a>]
<p>
Article 4 : <b>Covid-19 Government Response Tracker: A Dynamic Comparative Reflection of Global Performance</b><br>
co-authored with Dr Dhesi Raja and Dr Adlan Suhaimi
<br>
[<a href="https://github.com/khairulomar/Covid-19/blob/master/malaysia/Malaysia_gov_benchmark.md">My Github 1</a>] 
[<a href="https://github.com/khairulomar/Covid-19/blob/master/malaysia/Malaysia_gov_benchmark_2.md">My Github 2</a>] 
[<a href="https://www.ydlmalaysia.com/covid-19-government-response-tracker-a-dynamic-comparative-reflection-of-global-performance/
  ">YDL Publication</a>]
