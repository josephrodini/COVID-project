# COVID-project

An analysis of economic predictors of COVID data

## Segment One Obejctives

The following objectives are met below
- Presentation
- GitHub repository
- Machine learning model
- Database integration

## Presentation

### Overview

The entire world was rocked by the COVID-19 pandemic. Although there was little to no control over the origins of the virus, it might be possible to determine factors that help contain and control its spread. This project seeks to investigate whether underlying economic factors can predict COVID statistics.

### Motivation/Rationale

I am interested in public health for a number of reasons, mainly because it affects the entire population. I chose to investigate the COVID-19 pandemic as it has been at the forefront of every individual's life for the better part of three years, and continues to impact everyday existence. In order to prevent more devistating impacts from the virus, I decided to collect economic data as well as COVID statistics to try to find relationships between them. 

### Data Sources

There were four main sources that comprised this analysis:

- Data on county vaccination rates from https://data.cdc.gov/Vaccinations/COVID-19-Vaccinations-in-the-United-States-County/8xkx-amqh
- Data on county cases and deaths numbers from https://github.com/nytimes/covid-19-data
- Data on county economic factors from https://www.ers.usda.gov/data-products/county-level-data-sets/download-data/
- Data on county coordinates and population from https://simplemaps.com/data/us-counties

All four data sources are CSV files

### Analysis Questions

The final, cleaned dataset contains the predictors of unemployment rate and median income and the outcomes of COVID cases, COVID deaths, and COVID vaccination rates, along with some other summary statistics such as population. Questions to be considered include:

- Does unemployment rate predict COVID outcomes?
- Does median income predict COVID outcomes?
