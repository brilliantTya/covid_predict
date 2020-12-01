# Checklist



*   Preliminarily narrowed down the choices for datasets. (Apple Mobility Data, Oxford Government Response Tracker, Time Series of COVID-19 by DataHub, COVID data by OWID).
    #### Update 12/1: We decided to drop Apple Mobility Data due to its sparsity compared to other datasets.
*   Finished analyzing and preprocessing of Apple Mobility Data
    *   Fill in the null data with feasible data
    *   Aggregated data by region/country and transportation type (transit, driving, walking)
*   Finished preprocessing OWID Data - Constant and TimeSeries
*   Started analyzing Oxford Government Response Data
    *   Feature selection (Stringency Index, Government Response Index, etc.)
    *   Aggregate by country/region
*   We now have features:
    *   <span style="text-decoration:underline;">Constant</span>
      1. population
      2. population_density
      3. median_age
      4. aged_65_older
      5. aged_70_older
      6. gdp_per_capita
      7. extreme_poverty
      8. cardiovasc_death_rate
      9. diabetes_prevalence
      10. female_smokers
      11. male_smokers
      12. handwashing_facilities
      13. hospital_beds_per_thousand
      14. life_expectancy
      15. Human_development_index
    *   <span style="text-decoration:underline;">TimeSeries</span>
      1. total_cases
      2. new_cases
      3. new_cases_smoothed
      4. total_deaths
      5. new_deaths
      6. new_deaths_smoothed
      7. total_cases_per_million
      8. new_cases_per_million
      9. new_cases_smoothed_per_million
      10. total_deaths_per_million
      11. new_deaths_per_million
      12. new_deaths_smoothed_per_million
      13. total_tests
      14. new_tests
      15. total_tests_per_thousand
      16. new_tests_per_thousand
      17. new_tests_smoothed
      18. new_tests_smoothed_per_thousand
      19. tests_per_case
      20. positive_rate
      21. tests_units
      22. Stringency_index


# Data Stylesheet



*   Country and date data should be preprocessed into the form country * date.
*   Date in all tables should be in the form ‘yyyy-mm-dd’
*   Country information in our dataset should be in ISO form to avoid typo.


# The Problem, our big idea



*   A multifactor representation of covid-19 new cases. We want to include multi-field variables such as mobility, government policies, and population density.
*   A lot of previous works focus on the impact of covid-19 to these factors. We propose that these factors will, in turn, affect the spread of the virus, thus working to develop a model that uses new covid cases as a y-factor, predicting it using multiple x’s.
*   Possible impacts: while most governments implement policies on a theoretical basis, we believe our model would serve as a great empirical study to the existing data, underlining the factors with heavier weights in battling the pandemic.


# Our Goal

Lining out the relationship between confirmed COVID-19 cases and each country’s distinct statuses (including politics, government responses, natural conditions etc) and trying to set up a working model to predict future growth under different cases.


# Features of Interest



*   Past country-wise covid-19 cases.
*   Regimes
*   Government Responses
*   Weather
*   Population density & mobility
*   Media (information on the internet), public opinions, etc.
*   Medical Strength


# Expected Outcome


### Minimal Outcome

Integrate multiple sources of and different types of data to obtain country-wise information. Use the data to construct the relationship between various factors and the infected population. Conclude effective determinants of containing the spread of virus.


### Stretched Outcome

Based on the relationship we obtained, construct a prediction model with input parameters like weather, population mobility, policy stringency, etc..Visualize the outcome with charts. Include challenging features and data points like public opinion (natural language).


# Implementation Plan


#### 11/3

Devise the project plan. Understand the intrinsic shape of our data collection. Start preprocessing and conclude the traits of our data. Select the features of interest.


#### 11/13

Finish preprocessing. Research on scholarly articles of regression and model building.


#### 11/23

Code our model.


#### 12/3

Tweak our model.


#### 12/13

Complete stretched goals such as visualization.


# Polity Data

Index of democracy:

[https://ourworldindata.org/democracy](https://ourworldindata.org/democracy)

What regimes are all the country in 2016? The csv is in our folder: [https://drive.google.com/file/d/11IILbAYnCZ7fYcCaoxHvNv7stDxoa9FS/view?usp=sharing](https://drive.google.com/file/d/11IILbAYnCZ7fYcCaoxHvNv7stDxoa9FS/view?usp=sharing)

Polity IV Individual Country Regime Trends, 1946-2013: [http://www.systemicpeace.org/polity/polity4.htm](http://www.systemicpeace.org/polity/polity4.htm)

Polity Data Archive (Outdated?): 

[http://www.ksgleditsch.com/polity.html](http://www.ksgleditsch.com/polity.html)

Democracy Index (quite authoritative): 

[https://www.eiu.com/topic/democracy-index](https://www.eiu.com/topic/democracy-index)


# COVID & GOV Response

Github open data on Covid-19:

[https://github.com/datasets/covid-19](https://github.com/datasets/covid-19)

[https://datahub.io/core/covid-19#data](https://datahub.io/core/covid-19#data)

Apple Mobility Data:

[https://covid19.apple.com/mobility](https://covid19.apple.com/mobility)

Oxford COVID Gov Response Tracker Official:

[https://www.bsg.ox.ac.uk/research/research-projects/coronavirus-government-response-tracker](https://www.bsg.ox.ac.uk/research/research-projects/coronavirus-government-response-tracker)

Government Stringency Index (in our folder): [https://drive.google.com/file/d/14_8riS1fCSDN54FFOP226rHaSNnflZl_/view?usp=sharing](https://drive.google.com/file/d/14_8riS1fCSDN54FFOP226rHaSNnflZl_/view?usp=sharing)

Risk of Openness Github project:

[https://github.com/OxCGRT/covid-policy-scratchpad/tree/master/risk_of_openness_index](https://github.com/OxCGRT/covid-policy-scratchpad/tree/master/risk_of_openness_index)

The COVID19 Government Measures Dataset puts together all the measures implemented by governments worldwide in response to the Coronavirus pandemic. Data collection includes secondary data review. The researched information available falls into five categories:



*   Social distancing
*   Movement restrictions
*   Public health measures
*   Social and economic measures
*   Lockdowns

[https://www.kaggle.com/barun2104/government-measures-to-combat-covid19](https://www.kaggle.com/barun2104/government-measures-to-combat-covid19)

Policies to reduce the transmission of COVID-19:

[https://www.kaggle.com/paultimothymooney/covid19-containment-and-mitigation-measures](https://www.kaggle.com/paultimothymooney/covid19-containment-and-mitigation-measures)

Assessment Capacities Project COVID-19 government measures dataset:

[https://www.kaggle.com/chrischow/demographic-factors-for-explaining-covid19](https://www.kaggle.com/chrischow/demographic-factors-for-explaining-covid19)

Country level metadata that includes temperature, COVID-19 and H1N1 cases, etc. 

[https://www.kaggle.com/bitsnpieces/covid19-country-data](https://www.kaggle.com/bitsnpieces/covid19-country-data)


# General Country Data

Country names linked to region, population, area size, GDP, mortality and more: [https://www.kaggle.com/fernandol/countries-of-the-world](https://www.kaggle.com/fernandol/countries-of-the-world) (available in the folder)

World Bank WDI 2.12 - Health Systems:

[https://www.kaggle.com/danevans/world-bank-wdi-212-health-systems](https://www.kaggle.com/danevans/world-bank-wdi-212-health-systems)
