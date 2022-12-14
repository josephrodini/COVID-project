# COVID-project

An analysis of economic predictors of COVID-19 outcomes

## Project Overview

### Background

The entire world was rocked by the COVID-19 pandemic. Although there was little to no control over the origins of the virus, it might be possible to determine factors that have helped contain and control its spread. This project seeks to investigate whether underlying economic factors can predict COVID outcomes.

### Motivation/Rationale

I am interested in public health for a number of reasons, mainly because it affects the entire population. I chose to investigate the COVID-19 pandemic as it has been at the forefront of every individual's life for the better part of three years, and continues to impact everyday existence. In order to prevent more devistating impacts from the virus, I decided to collect economic data as well as COVID statistics to try to find relationships between them. 

### Analysis Questions

The final, cleaned dataset contains the predictors of unemployment rate and median household income and the outcomes of COVID cases per 100,000 people, COVID deaths per 100,000 people, and COVID vaccination rates expressed as a percentage. Using these variables, I am interested in seeing whether the economic measures can predict the COVID outcomes.


### Deliverables

- Presentation
- Database
- Machine learning models
- Dashboard


### Technology

- Coding: Python, Pandas in Jupyter Notebook; SQLAlchemy
- Database: PostgreSQL in PgAdmin
- Visualizations: Tableau, Plotly


### Data Sources

There were four main sources that comprised this analysis:

- Data on county vaccination rates from https://data.cdc.gov/Vaccinations/COVID-19-Vaccinations-in-the-United-States-County/8xkx-amqh
- Data on county cases and deaths numbers from https://github.com/nytimes/covid-19-data
- Data on county economic factors from https://www.ers.usda.gov/data-products/county-level-data-sets/download-data/
- Data on county coordinates and population from https://simplemaps.com/data/us-counties

All four data sources are CSV files


## Analysis

### Code from Jupyter Notebook

- [Requirements.txt](https://github.com/josephrodini/COVID-project/blob/main/requirements.txt) for Anaconda environment
- [ETL process for all four data files](https://github.com/josephrodini/COVID-project/blob/main/ETL/COVID_data_cleaning.ipynb)
- [Logistic regression models](https://github.com/josephrodini/COVID-project/blob/main/Machine_Learning/Logistic_Regression.ipynb)
- [Support vector machines](https://github.com/josephrodini/COVID-project/blob/main/Machine_Learning/SVM.ipynb)


### Initial Data Exploration

The four data files were cleaned, mostly meaning null values were dropped and columns renamed so they could be merged. About 5% of all deaths reported were lost due to the dropped values, but most of those came from Puerto Rico and Guam, territories that were outside the purview of this project. Files were exported from Python Pandas to CSV files.

### PostgreSQL Database

- The CSV files were loaded into tables in PostgreSQL accessed through PGAdmin. This was a locally hosted database. In addition to making and merging the tables, the calculated columns of cases per 100,000 people and deaths per 100,000 people were created.

- [Queries to create the tables](https://github.com/josephrodini/COVID-project/blob/main/SQL/creating_tables)

- [Queries to join tables and create the cases and deaths per 100,000 people](https://github.com/josephrodini/COVID-project/blob/main/SQL/merging_tables)

- ERD below

![ERD](https://github.com/josephrodini/COVID-project/blob/90dfbe7b35947e681264e41b09a12d28be1e9679/Images/COVID-projectDBD.png)

### Machine Learning

First, logistic regressions were performed to see if the economic variables of unemployment rate and median household income could predict COVID-19 outcomes. 

- Logistic regression predicting Cases per 100,000 People

![LRCases](https://github.com/josephrodini/COVID-project/blob/90dfbe7b35947e681264e41b09a12d28be1e9679/Images/RegCases.PNG?raw=true)

- Logistic regression predicting Deaths per 100,000 People

![LRDeaths](https://github.com/josephrodini/COVID-project/blob/90dfbe7b35947e681264e41b09a12d28be1e9679/Images/RegDeaths.PNG?raw=true)

- Logistic regression predicting Vaccination Rate

![LRVax](https://github.com/josephrodini/COVID-project/blob/90dfbe7b35947e681264e41b09a12d28be1e9679/Images/RegVax.PNG?raw=true)

Next, to compare logistic regression to a supervised machine learning model, support vector machines were used to test the predictive power of the economic variables. To briefly summarize, the SVMs were nearly identical in performance to the linear regressions, showing 55.3% accuracy for cases per 100,000, 72.9% accuracy for deaths per 100,000, and 65% for vaccination rate. So, although they work differently, they arrived at the same conclusion.

## Results


### Success of Predictors

- Case rate was not well-predicted by economic indicators, meaning that the spread of COVID was fairly uniform across the country regardless of economic level.

- However, death rate was well predicted by economic indicators, demonstrating that counties with more economic resources were better able to mitigate the pernicious effects of the pandemic.

- Vaccination rate was somewhat well predicted by economic indicators, suggesting that counties with more economic resources did somewhat of a better job getting their populations vaccinated.


### Tableau Dashboard

- Link: [COVID-project visualizations](https://public.tableau.com/app/profile/joe.rodini/viz/COVID-projectvisualizations/COVID-project#1)

### Presentation 

- Click here to see the slides [as a PDF]() or [as a Powerpoint file (Powerpoint contains speaker notes)](https://github.com/josephrodini/COVID-project/blob/segment-4/Presentation/COVID-project.pptx).

- Click [here](https://youtu.be/DoPG6PcMDro) to see presentation video.

## Summary

### Conclusions

- Top accuracy score: Logistic regression of unemployment and median income predicting deaths per 100,000 people: 73.3%
- Logistic regression and SVM performed almost identically

### Additional Analysis

- Factors that might have obscured the relationship between economic predictors and COVID outcomes might include: population density, political affiliation, education level, and ethnicity.

- Correlation is not necessarily causation???it could be that other variables, such as the ones above, cause the economic predictors and COVID outcomes to show a relationship.






