# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Testing, Statistical Summaries and Inference

### By Alexis Lim, DSI-16

## Problem Statement

What relationships can we identify in state average participation rates and average subject/total scores for the SAT and ACT in 2018? How can we work to increase participation rates in selected states and what are the criteria for the states we should focus on?

## Executive Summary

### Contents:
- 2017 Data Import and Cleaning
- 2018 Data Import and Cleaning
- Exploratory Data Analysis
- Data Visualization
- Data Dictionary
- Descriptive and Inferential Statistics
- Outside Research
- Conclusions and Recommendations

### Data Sources:
- [2017 SAT Scores by State](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/)
- [2017 ACT Scores by State](https://www.act.org/content/dam/act/unsecured/documents/cccr2017/ACT_2017-Average_Scores_by_State.pdf)
- [2018 SAT Scores by State](https://git.generalassemb.ly/dsi-sg-16/classes/blob/master/Project1234/project_1/data/sat_2018.csv) (Provided by General Assembly)
- [2018 ACT Scores by State](https://git.generalassemb.ly/dsi-sg-16/classes/blob/master/Project1234/project_1/data/act_2018_updated.csv) (Provided by General Assembly)

## Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|ACT & SAT|The U.S. state for which the data applies.|
|sat17_participation|float|SAT 2017|The state's participation rate for the 2017 SAT.|
|sat17_readingwriting|int|SAT 2017|The state's mean score for the Evidence-Based Reading & Writing component of the 2017 SAT.|
|sat17_math|int|SAT 2017|The state's mean score for the Math component of the 2017 SAT.|
|sat17_total|int|SAT 2017|The state's mean total score for the 2017 SAT.|
|act17_participation|float|ACT 2017|The state's participation rate for the 2017 ACT.|
|act17_english|float|ACT 2017|The state's mean score for the English component of the 2017 ACT.|
|act17_math|float|ACT 2017|The state's mean score for the Math component of the 2017 ACT.|
|act17_reading|float|ACT 2017|The state's mean score for the Reading component of the 2017 ACT.|
|act17_science|float|ACT 2017|The state's mean score for the Science component of the 2017 ACT.|
|act17_composite|float|ACT 2017|The state's mean composite score for the 2017 ACT.|
|sat18_participation|float|SAT 2018|The state's participation rate for the 2018 SAT.|
|sat18_readingwriting|int|SAT 2018|The state's mean score for the Evidence-Based Reading & Writing component of the 2018 SAT.|
|sat18_math|int|SAT 2018|The state's mean score for the Math component of the 2018 SAT.|
|sat18_total|int|SAT 2018|The state's mean total score for the 2018 SAT.|
|act18_participation|float|ACT 2018|The state's participation rate for the 2018 ACT.|
|act18_english|float|ACT 2018|The state's mean score for the English component of the 2018 ACT.|
|act18_math|float|ACT 2018|The state's mean score for the Math component of the 2018 ACT.|
|act18_reading|float|ACT 2018|The state's mean score for the Reading component of the 2018 ACT.|
|act18_science|float|ACT 2018|The state's mean score for the Science component of the 2018 ACT.|
|act18_composite|float|ACT 2018|The state's mean composite score for the 2018 ACT.|
|sat_part_difference|float|Final Dataset|The state's SAT participation rate change from 2017 to 2018.|
|act_part_difference|float|Final Dataset|The state's ACT participation rate change from 2017 to 2018.|
|average_part17|float|Final Dataset|The state's average participation rate across both tests in 2017.|
|average_part18|float|Final Dataset|The state's average participation rate across both tests in 2018.|
|sat_totalchange|int|Final Dataset|The state's SAT mean total score change from 2017 to 2018.|
|act_totalchange|float|Final Dataset|The state's ACT mean total score change from 2017 to 2018.|

## Conclusion & Recommendations

*Key Takeaways & Recommendations*

From the data, the states with highest growth in SAT participation rates had extremely high participation rates in the ACT in 2017. To ensure the most success, we should look at states with existing high participation in the ACT and convince them to switch to the SAT as their state accountability test. We should also consider the existing SAT participation rate as the two states Illinois and Colorado had SAT participation rates of around 10% in 2017, indicating that the test already had some traction.

A good example of this would be Montana, which has a SAT participation rate of 10% in 2018 and has a 100% participation rate in the ACT. It is [one of the states that administers the ACT state-wide](https://www.testive.com/state-sat-act/). The College Board should consider working with the state education board of Montana and lobby them to switch to the SAT as their state accountability exam.

Another potential state to work with would be Utah, which also has a low SAT participation rate of 4% in 2018 and 100% ACT participation rate. Despite the low participation rate, Utah's mean SAT test scores are relatively low and saw a large decrease from 2017 to 2018. It would be a good opportunity to reach out to the state education board to discuss how College Board could work together to help Utah's students be more prepared for the SAT test, given the national significance of SAT scores.

*Additional Data*

Additional data that would have been useful for this analysis are the following:
- Categorical variable on state policies toward standardized testing (e.g. Mandates testing: Yes/No; which state-administered test if any)
- Data from preceding and subsequent years such that we could examine a trend in the data over time.
- More granular data at the county or school-level that would have allowed us more data points to examine the trends in test scores and participation rates.
