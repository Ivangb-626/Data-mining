# Problems
This file is for addressing the problems regarding the project's last feedback

## Problem 1: Weather
Professor's feedback:

First, please clarify how exactly you intend to incorporate weather information. Are you considering weather forecasts at the departure airport, arrival airport, or both? Also, please verify that historical forecasts issued before your prediction cutoff are actually available. Keep in mind that multiple flights departing from the same airport around the same time will share very similar weather conditions, so there may be considerable redundancy across observations.

#### Proposed solution
**TODO**

## Problem 2: Temporal features
Professor's feedback:

Second, please consider extracting separate temporal features from the scheduled departure date and time, such as weekday, month, and hour of day. These should help your models identify recurring temporal patterns more easily.

#### Proposed solution
We decompose the scheduled departure date and time into separate features

Feature	   Source	   Values
Month	   FlightDate	1–12
Day of week	FlightDate	0–6
Day of month	FlightDate	1–31
Scheduled departure hour	CRSDepTime	0–23
Scheduled arrival hour	CRSArrTime	0–23
Holiday proximity	FlightDate + U.S. federal holiday calendar	flag for ±2 days around a holiday

## Problem 3: Aircraft-specific features
Professor's feedback:

Third, please consider whether you have sufficient historical observations to construct meaningful aircraft-specific delay features. Given your restriction to flights between the 15 busiest airports and a dataset of approximately 50,000 observations, individual aircraft may appear only a few times. This could make historical delay statistics unreliable or unavailable for many flights. Furthermore, using individual aircraft tail numbers as categorical features could introduce a large number of distinct categories, potentially resulting in high-dimensional encodings with relatively few observations per category. As an alternative or additional feature, you could consider aircraft types or models, which would likely provide a more manageable and generalizable representation. Since your dataset includes aircraft tail numbers, it may be possible to retrieve the corresponding aircraft models automatically from an external source, such as the FAA aircraft registry.

#### Proposed solution
**TODO**

## Problem 4: Route distribution
Professor's feedback:

Fourth, narrowing the scope to the 15 busiest airports is reasonable, but please check the actual distribution of observations across routes. Even with only 15 airports, there are 210 possible directed connections between distinct airports (or 105 undirected airport pairs). Your revised proposal still mentions approximately 50,000 records, which may be relatively limited for some connections, especially since flight frequencies are unlikely to be distributed uniformly. You could either sample your training data to achieve a more balanced representation of different routes or preserve their natural frequency distribution. Both approaches have advantages and disadvantages, so it would be interesting to consider how this choice affects your models and the interpretation of their performance. In either case, the test set should reflect the distribution of flights in your intended prediction scenario.

#### Proposed solution
**TODO**

## Problem 5: Regression
Professor's feedback:

Finally, please specify which regression algorithms you intend to use for your secondary task. The current proposal lists models primarily in the context of classification, so it would be helpful to clarify whether you intend to use their regression counterparts.

#### Proposed solution
Using the **regression counterpart** of each model, if for classification we use DecisionTree, we do **DecisionTree Regression**