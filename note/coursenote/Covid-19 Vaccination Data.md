# Potential Analyses: Covid-19 Vaccination


![](https://images.unsplash.com/photo-1625833017043-21a7642b9152?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1249&q=80)



# Verdict of the Dataset/Topic
This is a topic that can be expanded into different aspects (e.g. healthcare, social & welless of residents, economy, etc). The world-level dataset is highly structured and do no need professional knowledge to understand. The dataset is licensed under Creative Common and can be used for DAT, see [[#Usage of Data Source]].

There are quite a number of analyses and dashboards have been created using the same dataset by media, news publishers, data science forums. With these existing dashboards and rather limited set of common questions surrounding vaccination topic, it may cause the preconception among the participants, thus risking to chance to have dashboards that are highly similar across the different teams. 

A way mitigate this is possibly to require to the teams to combine at least another aspect into the analyses, by using a complementing dataset (e.g. economy or wellness). 

## Pro:

- ** Structured & Cleaned**: The (world) data sources on vaccination, testing, confirmed cases are highly structured, and in the form the ready for analysis, with little data cleansing to need be done.
-  **Variety of Fields**: Beside the core vaccination data, there are many other related fields, like country-level demographic, hospital ICU cases. This means there are many possible analyses that participants that can potentially come out with, if their itention is to try to avoid similar analyses.
## Con:
- **Require Contextual Background**: The team with richer contextual knowledge, to add as additional data to the analyses, like when and what are the different policies were rolled out: when different age-groups started to vaccine, reopening policy will be able to much effectively analyze the dataset.


- **Sensitivity**: topic of vaccination unevitably to interpret as the ability of the government in rolling out the vaccination program effectively. The vaccination choice of different demographics may 
---
## Data Readiness: ⭐⭐⭐⭐⭐
## Easiness to Analyze: ⭐⭐⭐
## Potential for Creative Analyses: ⭐⭐⭐
	Note: these are based on the world-level data and assuming if the team only use this as the sole data for analyses.

---
# Potential Questions
** Vaccination Process & Rate**
1. What is the proportion of the different covid-19 vaccines used in Singapore?

> Vaccination data, segmented by brands.
> If possible, breakdown by different age-cohorts and/or vaccination centers.

2. Is Singapore one of the countries that reaches high vaccination rate in short amount of time?
	- Who are the early adopter, majority, and late adopter of vaccinations (Note that different age-groups' have different start time for the vaccination period)?
	- Does people commute further to get their choice of vaccine?
	
> Vaccination data at the individual-level or cohort-level or segmented by planning area level or finer.


1. Does vaccination reduce the covid-19 cases in Singapore and in other countries
	- Does higher vaccination rate leads to less confirmed cases?
	- Does higher vaccination rate leads to less cases that need ICU care?

> - Vaccination rate.
> - Confirmed Cases
> - ICU Cases
> - Other healthcare-related factors that can reflect the loads on the healthcare system


4. The occurance of vaccination's side-effects may have been overstated due to the media effects. Is there any data-backed ev shows the side-effects are rare circumstance and mostly mild conditions?

> - Vaccination rate.
> - Number and profiles of those with adverse effects after vaccination
>

**Lifestyle & Economy:**

1. How does the vaccination lead to the reopening of economy and social activities in Singapore and the other part of the worlds?


>This is the part require another dataset for complementing the analyses. Few options can be explored further:
>
> - **LTA's DataMall** can be used to retrieved the following to estimate the economy/activties: i) passenger volume of buses and trains, ii) availability of car parks, iii) taxi availability
> - **Job Vaccancy** from SG Career as one of the rough indication of the economy reopening

2. What are the change in sentiments of residents  (Singapore and/or other countries) before and after mass vaccination? (e.g. from worried/depress to relief)


> Not sure if there is a database for the services that collect residents' feedback/posts from gov-managed social sites.


Again, these are just example questions. We can be opportunitics and see what are the datasets that are more readily available / easier to get, then revise on what are the "complementing" analyses can be, especially if you all think this part is needed.


---
# Data Source for World-level 

## Vaccinations
| Variable                                | Description                                                                                                                                                                                                                                                                                                                                       |
|:----------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `total_vaccinations`                    | Total number of COVID-19 vaccination doses administered                                                                                                                                                                                                                                                                                           |
| `people_vaccinated`                     | Total number of people who received at least one vaccine dose                                                                                                                                                                                                                                                                                     |
| `people_fully_vaccinated`               | Total number of people who received all doses prescribed by the vaccination protocol                                                                                                                                                                                                                                                              |
| `total_boosters`                        | Total number of COVID-19 vaccination booster doses administered (doses administered beyond the number prescribed by the vaccination protocol)                                                                                                                                                                                                     |
| `new_vaccinations`                      | New COVID-19 vaccination doses administered (only calculated for consecutive days)                                                                                                                                                                                                                                                                |
| `new_vaccinations_smoothed`             | New COVID-19 vaccination doses administered (7-day smoothed). For countries that don't report vaccination data on a daily basis, we assume that vaccination changed equally on a daily basis over any periods in which no data was reported. This produces a complete series of daily figures, which is then averaged over a rolling 7-day window |
| `total_vaccinations_per_hundred`        | Total number of COVID-19 vaccination doses administered per 100 people in the total population                                                                                                                                                                                                                                                    |
| `people_vaccinated_per_hundred`         | Total number of people who received at least one vaccine dose per 100 people in the total population                                                                                                                                                                                                                                              |
| `people_fully_vaccinated_per_hundred`   | Total number of people who received all doses prescribed by the vaccination protocol per 100 people in the total population                                                                                                                                                                                                                       |
| `total_boosters_per_hundred`            | Total number of COVID-19 vaccination booster doses administered per 100 people in the total population                                                                                                                                                                                                                                            |
| `new_vaccinations_smoothed_per_million` | New COVID-19 vaccination doses administered (7-day smoothed) per 1,000,000 people in the total population                                                                                                                                                                                                                                         |

## Tests & positivity
| Variable                          | Description                                                                                                                                                                                                                                                                                                          |
|:--------------------------------- |:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `total_tests`                     | Total tests for COVID-19                                                                                                                                                                                                                                                                                             |
| `new_tests`                       | New tests for COVID-19 (only calculated for consecutive days)                                                                                                                                                                                                                                                        |
| `total_tests_per_thousand`        | Total tests for COVID-19 per 1,000 people                                                                                                                                                                                                                                                                            |
| `new_tests_per_thousand`          | New tests for COVID-19 per 1,000 people                                                                                                                                                                                                                                                                              |
| `new_tests_smoothed`              | New tests for COVID-19 (7-day smoothed). For countries that don't report testing data on a daily basis, we assume that testing changed equally on a daily basis over any periods in which no data was reported. This produces a complete series of daily figures, which is then averaged over a rolling 7-day window |
| `new_tests_smoothed_per_thousand` | New tests for COVID-19 (7-day smoothed) per 1,000 people                                                                                                                                                                                                                                                             |
| `positive_rate`                   | The share of COVID-19 tests that are positive, given as a rolling 7-day average (this is the inverse of tests_per_case)                                                                                                                                                                                              |
| `tests_per_case`                  | Tests conducted per new confirmed case of COVID-19, given as a rolling 7-day average (this is the inverse of positive_rate)                                                                                                                                                                                          |
| `tests_units`                     | Units used by the location to report its testing data                                                                                                                                                                                                                                                                |
|                                   |                                                                                                                                                                                                                                                                                                                      |
## Confirmed cases
| Variable                         | Description                                                           |
|:---------------------------------|:----------------------------------------------------------------------|
| `total_cases`                    | Total confirmed cases of COVID-19                                     |
| `new_cases`                      | New confirmed cases of COVID-19                                       |
| `new_cases_smoothed`             | New confirmed cases of COVID-19 (7-day smoothed)                      |
| `total_cases_per_million`        | Total confirmed cases of COVID-19 per 1,000,000 people                |
| `new_cases_per_million`          | New confirmed cases of COVID-19 per 1,000,000 people                  |
| `new_cases_smoothed_per_million` | New confirmed cases of COVID-19 (7-day smoothed) per 1,000,000 people |
## Confirmed deaths
| Variable                          | Description                                                             |
|:--------------------------------- |:----------------------------------------------------------------------- |
| `total_deaths`                    | Total deaths attributed to COVID-19                                     |
| `new_deaths`                      | New deaths attributed to COVID-19                                       |
| `new_deaths_smoothed`             | New deaths attributed to COVID-19 (7-day smoothed)                      |
| `total_deaths_per_million`        | Total deaths attributed to COVID-19 per 1,000,000 people                |
| `new_deaths_per_million`          | New deaths attributed to COVID-19 per 1,000,000 people                  |
| `new_deaths_smoothed_per_million` | New deaths attributed to COVID-19 (7-day smoothed) per 1,000,000 people |


## Policy responses
| Variable           | Description                                                                                                                                                                                                         |
|:-------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `stringency_index` | Government Response Stringency Index: composite measure based on 9 response indicators including school closures, workplace closures, and travel bans, rescaled to a value from 0 to 100 (100 = strictest response) |
                                                              



# Usage of Data Source
- All visualizations, data, and code produced by Our World in Data are completely open access under the [Creative Commons BY license](https://creativecommons.org/licenses/by/4.0/) 
- This means DSAI have the permission to use, distribute, and reproduce these in any medium, provided the source and authors are credited. [source](https://ourworldindata.org/faqs#how-is-your-work-copyrighted)

---
# Reference
- *Our World in Data* Official Page https://ourworldindata.org/covid-vaccinations
- Covid-19 Dataset https://github.com/owid/covid-19-data
- A global database of COVID-19 vaccinations https://www.nature.com/articles/s41562-021-01122-8
- Covid vaccines: How fast is progress around the world? https://www.bbc.com/news/world-56237778
- Analysis Example 1: Covid-19 Vaccination https://www.analyticsvidhya.com/blog/2021/05/covid-19-vaccination-data-analysis-visualization/
- Analysis Example 2: https://towardsdatascience.com/covid-19-vaccination-progress-analysis-around-the-world-736d7e57f198