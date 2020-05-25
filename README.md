# COVID-19 Exploration: Early spread in Q1 2020
Meagan Rossi & Jigme Sherpa

## Overview
A novel coronavirus is a new coronavirus that has not been previously identified. COVID-19 was first identified in Wuhan, China at the end of 2019. Tracking data is available from Jan 22, 2020 to the current date.

From the Centers for Disease Control and Prevention:
> Delays in reporting can cause the number of COVID-19 cases reported on previous days to increase. (Sometimes this effect is
> described as “backfill.”) State, local, and territorial health departments report the number of cases that have been
> confirmed and share these data with CDC. Since it takes time to conduct laboratory testing, cases from a previous day may be > added to the daily counts a few days late.

Forecast rates of confirmed, recovered and death COVID19 cases using data from the Johns Hopkins University [COVID-19 Dashboard](https://coronavirus.jhu.edu/map.html). Data is extracted from Google Sheets and compiled into a csv.  Tracking data is available from Jan 22, 2020 to the current date.

Description | Case Count
------------ | -------------
Total Number of Countries | 205
Total Confirmed | 417,966
Total Recovered | 107,705
Total Fatalities | 18,615

Data was cleaned and manipulated in Python for further anaylsis with Sci-Kit Learn. Achieved data stationarity through log transformations and Dicky-Fuller testing. Model was trained through a hold-out set of one week. We related the present value of the timeseries to past values and past prediction errors.

## Autoregressive Integrated Moving Average (Best Model)
- Highest log likelihood
- Lowest AIC
- Order = (p,d,q) = (1,1,2)

<img src="/_Images/ARIMA.png" align="center" width="60%">

## Tools<br/>
- AR Timeseries Model
- MA Timeseries Model
- ARMA Timeseries Model
- ARIMA Timeseries Model

**Data Source**
1. Kaggle: [Novel Corona Virus 2019 Dataset](https://www.kaggle.com/sudalairajkumar/novel-corona-virus-2019-dataset)

**Column Descriptions**
- Sno - Serial number
- ObservationDate - Date of the observation in MM/DD/YYYY
- Province/State - Province or state of the observation (Could be empty when missing)
- Country/Region - Country of observation
- Last Update - Time in UTC at which the row is updated for the given province or country. (Not standardised and so please - clean before using it)
- Confirmed - Cumulative number of confirmed cases till that date
- Deaths - Cumulative number of of deaths till that date
- Recovered - Cumulative number of recovered cases till that date
