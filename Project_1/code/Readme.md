# Project 1: SAT & ACT Analysis

## Problem Statement

#### Background

US Universities require students to take either SAT or ACT and submit their scores to prospective universities. SAT faced intense competition from the ACT. Respond to this challenging situation, a new format for the SAT was released in March 2016. Our teams track statewide participation and report possible recommendations for improvements.

#### Problem
For years, Students in State North Dakota appeared to have a shallow SAT participation rate and high ACT participation rate. The organization would like to find possible ways to increase the participation rate in North Dakota.

#### Target Audience 
Non Technical executives from Marketing, adminstration, and senior managerment will join the discussion.

## Executive Summary

### Contents:
- [2017 Data Import & Cleaning](#Data-Import-and-Cleaning)
- [2018 Data Import and Cleaning](#2018-Data-Import-and-Cleaning)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Data Visualization](#Visualize-the-data)
- [Descriptive and Inferential Statistics](#Descriptive-and-Inferential-Statistics)
- [Outside Research](#Outside-Research)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)
- [References](#references)

## Data Dictionary

| feature                                     | type   | dataset   | description                                                                                                                                                |
|:--------------------------------------------|:-------|:----------|:----------------------------------------------------------------------------------------------------------------------------------------------------------|
| state                                       | object | SAT_2017/8| The State name in USA                                                                                                                                      |
| sat_participation_percentage_2017           | int    | SAT_2017  | The percentage of students took the SAT test for different states in 2017                                                                                  |
| sat_evidence_based_reading_and_Writing_2017 | int    | SAT_2017  | Average SAT ERW Section Score for participated students in different states in 2017                                                                        |
| sat_math_2017                               | int    | SAT_2017  | Average SAT Math Section Score for participated students in different states in 2017                                                                       |
| sat_total_2017                              | int    | SAT_2017  | Average SAT Total Section Score for participated students in different states in 2017                                                                      |
| act_participation_percentage_2017           | int    | ACT_2017  | The percentage of students took the ACT test for different states in 2017                                                                                  |
| act_english_2017                            | float  | ACT_2017  | Average ACT English Writing Section Score for participated students in different states in 2017                                                            |
| act_math_2017                               | float  | ACT_2017  | Average ACT math Section Score for participated students in different states in 2017                                                                       |
| act_reading_2017                            | float  | ACT_2017  | Average ACT reading Section Score for participated students in different states in 2017                                                                    |
| act_science_2017                            | float  | ACT_2017  | Average ACT science Section Score for participated students in different states in 2017                                                                    |
| act_composite_2017                          | float  | ACT_2017  | Average ACT composite Section Score for participated students in different states in 2017: composite score is the average score for all the section scores |
| sat_participation_percentage_2018           | int    | SAT_2018  | The percentage of students took the SAT test for different states in 2018                                                                                  |
| sat_evidence_based_reading_and_Writing_2018 | int    | SAT_2018  | Average SAT ERW Section Score for participated students in different states in 2018                                                                        |
| sat_math_2018                               | int    | SAT_2018  | Average SAT Math Section Score for participated students in different states in 2018                                                                       |
| sat_total_2018                              | int    | SAT_2018  | Average SAT Total Section Score for participated students in different states in 2018                                                                      |
| act_participation_percentage_2018           | int    | ACT_2018  | The percentage of students took the ACT test for different states in 2018                                                                                  |
| act_english_2018                            | float  | ACT_2018  | Average ACT English Writing Section Score for participated students in different states in 2018                                                            |
| act_math_2018                               | float  | ACT_2018  | Average ACT math Section Score for participated students in different states in 2018                                                                       |
| act_reading_2018                            | float  | ACT_2018  | Average ACT reading Section Score for participated students in different states in 2018                                                                    |
| act_science_2018                            | float  | ACT_2018  | Average ACT science Section Score for participated students in different states in 2018                                                                    |
| act_composite_2018                          | float  | ACT_2018  | Average ACT composite Section Score for participated students in different states in 2018: composite score is the average score for all the section scores |

## Conclusions and Recommendations

Surprisingly, we could find out college board offices located in states, and some of their nearby states tend to have higher SAT participation Rates. ACT inc located State, and some of its nearby states tend to have low SAT participation Rates but high ACT participation rates. Hence, the higher the college board team local accessibility will generally result in the higher SAT participation Rate. Also, most states show an increased SAT participation rate increment from 2017 to 2018 after the new format of SAT release is the College Board team located states or their nearby states. Market accessibility is essential for the Participation Rate changes.

To increase the SAT participation Rate in North Dakota, we need to understand the local market situation local policy closely works with local education firms. A local college board team in North Dakota or nearby North Dakota is necessary for this purpose.

Further, we could analyze some additional data from State SAT participation rates by different years, consolidate with college board offices launched years, and see how the Market accessibility will affect the local and neighborhood participation rate.
