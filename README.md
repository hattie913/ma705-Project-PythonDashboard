# MA705 Final Project

This repository contains files used in the MA705 dashboard project: 
"2021 Covid-19 Cases and Vaccinations in Most Populous States in the United States".

The final dashboard is deployed on Heroku [here](https://ma705covid19-project.herokuapp.com/)

## Dashboard Description

The dashboard demonstrates how Covid-19 cases and new doses of vaccinations implemented daily in some populous US states change over time since the vaccine began to deployed nationwide in January 2021. The dashboard collects real-time data in Massachusetts and the other top 10 most populated states in the US.

Users can compare and overview the change of vcaccination implementations and daily counts of Covid-19 cases across those big states on the real-time, interactive time series graph, and get more detailed information on the table at the bottom.


### Data Sources

Data from this dashboard was collected from [Centers for Disease Control and Prevention](https://covid.cdc.gov/covid-data-tracker/#cases_casesper100klast7days), and [Our World in Data](https://ourworldindata.org/us-states-vaccinations).

- Source of Covid-19 cases dataset: [Covid-19 cases from SODA API endpoint](https://data.cdc.gov/resource/9mfq-cb36.json)
- Source of US vaccination dataset: [US Vaccinations](https://github.com/owid/covid-19-data/tree/master/public/data/vaccinations)

The 'realtime_Covid.py' file generates the target dataset for analyzing. The raw datasets were first cleaned by dropping unnecessary rows of states and columns of variables, and filling missing values with 0s. Before merging the two datasets, the Covid-19 cases dataset was also cleaned by grouping 'NY' and 'NYC'on the same date and then add the aggregated daily data of the entire New York State to the original dataset. Having the identical state abbreviation, the two datasets were then merged on their state abbreviation and date, then the merged dataset was saved as a 'pkl' file for the downstream analysis. 


### Variable Interpretation: 

- "Daily vaccinations" : new doses administered per day (7-day smoothed).
- "Daily vaccinations/million": the number of new doses of vaccinations per million people in the total population of the state received each day.
-  "Total vaccinations": total number of doses administered. This is counted as a single dose, and may not equal the total number of people vaccinated, depending on the specific dose regime (e.g. people receive multiple doses). 

\* Variable interpretation is based on the original interpretation of the raw dataset.
For more detailed information, please refer to: https://github.com/owid/covid-19-data/edit/master/public/data/vaccinations/README.md 

                             
                          
