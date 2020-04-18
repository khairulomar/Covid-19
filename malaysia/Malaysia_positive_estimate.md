# Evaluating the reliability of the number of confirmed Covid-19 cases reported by countries

### Working assumptions
It can be hard to gauge the true extent of the spread of Covid-19 outbreak in each country since different countries have different resources and policies in conducting tests. In comparison, the number of deaths caused by the virus are more likely to be reported correctly as seriously ill individuals would seek medical attention, plus more rigorous reporting procedures in recording such cases.
Under-reported official positive cases from around the world can be caused by missing cases related to positive individuals who are asymptomatic and those who recovered at home without being tested. Low official figures can also be attributed to delays in reporting due to poor laboratory capabilities and other logistics issues.

### Evaluation methodology
Data for the number of Covid-19 deaths were gathered from John Hopkins University while the number of tests were derived from Our World in Data database.
By plotting the number of deaths vs. the number of confirmed cases and the number of tests performed, we ran linear regression models to find the relationship between the measures in question. Countries that lie close to or above the regression line can be interpreted as being more likely to have adequate testing and reporting policies when comparing to other countries with similar severity, as measured in the number of deaths. On the contrary, a given country can be interpreted as being more likely to have inadequate testing and reporting policies if it lies further away below the regression line.
We wish to emphasise that while this method may not be a guaranteed way in assessing the reliability of official figures by country, it could provide a guide in benchmarking a given country’s policies versus other comparable countries. Please exercise caution in interpreting the results as there may be other underlying factors at play that may not considered in the model.

### Are reported cases under-estimated?
In the analysing the number deaths versus the number of official positive cases, the area shaded in orange can be interpreted as countries where the official number of confirmed cases are more likely to be under-reported due to various reasons. Based on this method, we may have reasons to believe that the number of total cases reported for Malaysia so far can be used to represent the actual situation on the ground, especially when comparing with other countries with almost similar number of deaths such as Hungary and Ukraine.
<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/death_vs_confirmed.png">

### Are countries testing enough?
We can also benchmark if Malaysia is testing enough by looking at how other countries are performing. Similarly, as in the analysis above, we shall use the number of deaths to gauge the spread of the virus in the population instead of using the official confirmed cases figures. Using a regression line to find a relationship between the two, we can interpret that countries that lie below the line in the shaded area are more likely to be under-testing its population. South Korea and Germany, which have been praised by the WHO for their testing policies, are well above the regression line.
<p>
<img src="https://github.com/khairulomar/Covid-19/blob/master/img/test_vs_deaths.png">
