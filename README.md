# Flight-Arrival-Delay-Prediction

Flight delays have negative impacts, mainly economic, for passengers, airlines, and airports in terms of loss of opportunities, time, penalties, fines and additional operation costs, such as crew and aircrafts retentions in airports [1]. Moreover, flight delays lead to increase in taxi operations and in turn, increased fuel consumption and gas emissions. Prediction of flight arrival delay and estimation of delay time made right after take-off can be used for notifying passengers, crew and destination airport as well as runway traffic management, and workforce optimisation at the destination airport. The report analyses airline data and discusses development of classification and regression models for delay prediction and delay time estimation respectively.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A research funded by the Federal Aviation Administration analysed the 2007 U.S. flight data and found out that flight delays costed $8.3 billion to the airlines, around $16.7 billion to the passengers in lost time and efficiency and reduced the national gross economic output by $4 billion[2]. A flight's delayed arrival also impacts the taxi-in and taxi-out times of other flights. The plane is moving on its wheels using its own power during these times. In USA in 2007, taxi-out operations were responsible for 4,000 tons of hydrocarbons, 8,000 tons of nitrogen oxides and 45,000 tons of carbon monoxide emissions [3].

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Prediction of arrival delay time can help in air traffic management, runway usage and taxi operations management of flights arriving at the same time, route optimization to reduce potential delay, and workforce optimisation. This would lead to reduction in fuel consumption on ground, and reduction of potential losses to the airlines and passengers due to delays. The flight arrival delay prediction model will use the features relevant to a flight’s take-off, scheduled arrival, distance as well as other delay factors and predict arrival delay time. Two supervised data mining problems are considered- one is a binary classification problem predicting whether a flight will be delayed or not, another is a regression problem involving estimation of the arrival delay time in minutes.

## Datasets
**Carrier On-Time Performance Data**
The flight performance data is publically available on the website hosted by the Bureau of Transportation Statistics (BTS), which, as part of the United States Department of Transportation, compiles, analyses, and makes accessible information on the nation's transportation systems [4]. For approaching the delay prediction problem, the relevant data for all months of the year 2018 was downloaded [5]. Each month had over 500,000 instances. Each data instance from the initial dataset had over 60 attributes and corresponded to a single flight of any airline on a specific time of a day in a given month and year. The possible target variables were ARR_DELAY (difference in minutes between scheduled and actual arrival time; early arrivals show negative numbers) and ARR_DEL15 (Arrival Delay Indicator; 1=YES, 0=NO). The descriptions of relevant attributes are given in Table A below [6], [7].

**Weather Data**
Since information like the weather delay is not available before landing, this attribute was replaced by the information about the actual weather on the day of the flight, available from the NCDC’s (National Climactic Data Center) link to the ‘global summary of the day’ database. These summaries comprised of a dozen daily averages computed from Integrated Surface Data. Daily weather elements include mean values of temperature, dew point temperature, sea level pressure, station pressure, visibility, and wind speed plus maximum and minimum temperature, maximum sustained wind speed and maximum gust, precipitation amount, snow depth, and weather indicators [8]. Out of these, four attributes (sea level pressure, wind speed, precipitation and visibility) were chosen and downloaded from the search tool of the National Centers for Environmental Information (NCEI) website [9] for the entire year of 2018. Airport codes were used to extract the weather data of the required geographical location. The descriptions of chosen attributes are given in Table B below [10].

## Methodology

### Data Exploration
* [DataExploration1.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/DataExploration1.ipynb)
* [DataExploration2.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/DataExploration2.ipynb)
* [DataExploration3.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/DataExploration3.ipynb)
* [DataExploration4.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/DataExploration4.ipynb)

### Data Preparation
* [DataCleaning1.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/DataCleaning1.ipynb)
* [DataCleaning2.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/DataCleaning2.ipynb)
* [FeatureEngineering1.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/FeatureEngineering1.ipynb)
* [FeatureEngineering2.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/FeatureEngineering2.ipynb)
* [JoiningFeatures.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/JoiningFeatures.ipynb)

### Feature Selection
* [CorrelationHeatmap-FeatureSelection1.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/FeatureSelection1.ipynb)
* [FeatureImportances-FeatureSelection2.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/FeatureSelection2.ipynb)
* [UnivariateSelection-FeatureSelection3.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/FeatureSelection3.ipynb)

### Model Building and Evaluation
**Prediction of ARR_DEL15 or Arrival Delay Indicator (Classification Problem)**
> used: new file (processed_dataset.csv)
* [LogisticRegression.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/LogisticRegression.ipynb)
* [DecisionTree.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/DecisionTree.ipynb)
* [KNearestNeighbor.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/KNearestNeighbor.ipynb)
**Prediction of ARR_DELAY or exact arrival delay time in minutes (Regression Problem)**
> used: old file (most_final_dataset.csv)
* [PolynomialRegression.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/PolynomialRegression.ipynb)
* [MLPRegression.ipynb](https://github.com/ApurvaBhargava/Flight-Arrival-Delay-Prediction/blob/master/MLPRegression.ipynb)

## References
[1] Sternberg, Alice & Soares, Jorge & Carvalho, Diego & Ogasawara, Eduardo. (2017). A Review on Flight Delay Prediction.

[2] Ball, Michael & Barnhart, Cynthia & Dresner, Martin & Hansen, Mark & Neels, Kevin & Odoni, Amedeo & Peterson, Everett & Sherry, Lance & Trani, Antonio & Zou, Bo & Britto, Rodrigo & Fearing, Doug & Swaroop, Prem & Uman, Nitish & Vaze, Vikrant & Voltes, Augusto. (2010). Total Delay Impact Study: A Comprehensive Assessment of the Costs and Impacts of Flight Delay in the United States.

[3] Clewlow, Regina & Simaiakis, Ioannis & Balakrishnan, Hamsa. (2010). Impact of Arrivals on Departure Taxi Operations at Airports.10.2514/6.2010-7698.

[4] en.wikipedia.org/wiki/Bureau_of_Transportation_Statistics

[5] www.transtats.bts.gov/DL_SelectFields.asp?Table_ID=236

[6] https://transtats.bts.gov/printglossary.asp

[7] www.bts.gov/topics/airlines-and-airports/understanding-reporting-causes-flight-delays-and-cancellations

[8] www.ncdc.noaa.gov/isd/

[9] www.ncei.noaa.gov/access/search/data-search/global-summary-of-the-day

[10] www.ncdc.noaa.gov/crn/measurements.html

## Table A: Flight Performance Data Attributes and their Descriptions
| Attribute           | Description                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| YEAR                | Year of flight, 2018 in all cases                                                                                                                                                                                 |
| QUARTER             | Quarter of flight                                                                                                                                                                                                 |
| MONTH               | Month of flight                                                                                                                                                                                                   |
| DAY_OF_MONTH        | Day of the month of flight                                                                                                                                                                                        |
| DAY_OF_WEEK         | Day of the week of flight                                                                                                                                                                                         |
| FL_DATE             | Flight Date                                                                                                                                                                                                       |
| ORIGIN              | Flight Origin Airport Code                                                                                                                                                                                        |
| ORIGIN_CITY_NAME    | Flight Origin City Name                                                                                                                                                                                           |
| DEST                | Flight Destination Airport Code                                                                                                                                                                                   |
| DEST_CITY_NAME      | Flight Destination City Name                                                                                                                                                                                      |
| DEP_TIME            | Time of departure from origin, hhmm                                                                                                                                                                               |
| DEP_DELAY           | Delay in departure, in minutes                                                                                                                                                                                    |
| DEP_DEL15           | Departure delay indicator (1 if DEP_DELAY>=15, 0 otherwise)                                                                                                                                                       |
| DEP_DELAY_GROUP     | Group code indicating early, on-time or late departure                                                                                                                                                            |
| TAXI_OUT            | The time elapsed between departure from the origin airport gate and wheels off.                                                                                                                                   |
| WHEELS_OFF          | Time when flight had taken off, hhmm                                                                                                                                                                              |
| ARR_TIME            | Time of arrival at destination, hhmm                                                                                                                                                                              |
| ARR_DELAY           | Delay in arrival, in minutes                                                                                                                                                                                      |
| ARR_DEL15           | Arrival delay indicator (1 if ARR_DELAY>=15, 0 otherwise)                                                                                                                                                         |
| ARR_DELAY_GROUP     | Group code indicating early, on-time or late arrival                                                                                                                                                              |
| CANCELLED           | Cancelled Flight Indicator (1=Yes, 0=NO)                                                                                                                                                                          |
| CANCELLATION_CODE   | Specifies The Reason For Cancellation                                                                                                                                                                             |
| DIVERTED            | Diverted Flight Indicator (1=Yes, 0=NO)                                                                                                                                                                           |
| AIR_TIME            | Expected flight time, in minutes, assuming no issues                                                                                                                                                              |
| DISTANCE            | Expected distance to be covered                                                                                                                                                                                   |
| CARRIER_DELAY       | Delay due to circumstances within the airline's control (e.g. maintenance or crew problems, aircraft cleaning, baggage loading, fueling, etc.), in minutes                                                        |
| WEATHER_DELAY       | Delay due to weather, in minutes                                                                                                                                                                                  |
| NAS_DELAY           | Delay attributable to the national aviation system that refer to a broad set of conditions, such as non-extreme weather conditions, airport operations, heavy traffic volume, and air traffic control, in miuntes |
| SECURITY_DELAY      | Delay caused by evacuation of a terminal or concourse, re-boarding of aircraft because of security breach, inoperative screening equipment and/or long lines at screening areas, in minutes                       |
| LATE_AIRCRAFT_DELAY | Delay of a previous flight of the same aircraft, causing the present flight to depart late, in minutes                                                                                                            |
| TOTAL_ADD_GTIME     | Total Ground Time Away from Gate for Gate Return or Cancelled Flight                                                                                                                                              |
| LONGEST_ADD_GTIME   | Longest Time Away from Gate for Gate Return or Cancelled Flight                                                                                                                                                   |
| DIV_ARR_DELAY       | Difference in minutes between scheduled and actual arrival time for a diverted flight reaching scheduled destination. The ArrDelay column remains NULL for all diverted flights.                                  |
| DIV_DISTANCE        | Distance between scheduled destination and final diverted airport (miles). Value will be 0 for diverted flight reaching scheduled destination.                                                                    |

## Table B: Daily Weather Data Attributes and their Descriptions
| Attribute | Description                                                                                                                                                                                                                                                                                                                                  |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DATE      | Date for which the weather summary is given                                                                                                                                                                                                                                                                                                  |
| SLP       | It is the sea level pressure in mbar.                                                                                                                                                                                                                                                                                                         |
| WDSP      | Each station uses an anemometer to measure wind speed at a height of approximately 1.5 meters above the surface. Every five minutes, the datalogger averages two-second pulse counts to derive 5-minute average wind speed in meters per second (m/s).                                                                                       |
| PRCP      | Each station has a weighing precipitation gauge which is equipped with three load cell sensors to provide three independent measurements of depth change (in millimeters) at 5-minute intervals. The three series of 5-minute values are then used in an algorithm to derive the station's official 5-minute and hourly precipitation value. |
| VISIB     | It is the distance at which light or an object can be clearly discerned, as determined by weather conditions                                                                                                                                                                                                                                 |
