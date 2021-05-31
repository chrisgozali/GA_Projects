# Project 1

## Executive Summary

The College Entrance Examination Board (or "College Board") was founded in 1899 with the vision of creating standardized college entrance testing. The first SAT was conducted in 1929 and was based on an intelligence test first created for the US army in WWI. This was followed by several years of slow growth and College Board made several adjustments to the tests. During WWII, College Board administered SAT-like tests for vocational testing in the US navy. It was only after WWII that SAT testing had a breakthrough. A law had been passed to grant WWII veterans cash relief for college tuition. This incentivised many veterans to seek college education. With no other standardized testing method during the 1940-1950s the SATs experienced a sharp increase in the number of test takers.

The American College Testing (ACT) program was created in 1959. Its founders saw a need for a more widely used college testing system and one that measures academic preparation. At this point, the use of the SATs was mainly in northeastern US and not widespread enough. The ACTs included testing for English, Math, Natural Sciences as well as Social Studies, allowing for academic placement in addition to admissions.The ACTs eventually became a close competitor to the SATs, with the number of students taking the ACTs exceeding the number of students taking the SATs in 2010. ACT tests administered continued to rise sharply while SAT testing plateaued. This [chart:](https://www.erikthered.com/tutor/historical-sat-act-test-takers-both.pdf) shows the historical trends regarding the number of test takers for both tests.

With these tests being the two largest for standardized testing, most students would opt to pick one over the other. In 2016, the SATs were redesigned to better suit the needs of prospective students and colleges. These changes would hopefully encourage students to pick the SATs as their college entrance test of choice.

[Source: A (Mostly) Brief History Of The SAT And ACT Tests](https://www.erikthered.com/tutor/sat-act-history.html#y2011)

## Problem Statement

We are presented with the 2017 and 2018 SAT and ACT data by state. This project aims to identify trends between SAT/ACT participation rates, **determine suitable strategies to best improve SAT participation rates** and **narrow down the list of states College Board to most efficiently channel its resources**.

## Contents

- 2017 Data Import & Cleaning
- 2018 Data Import and Cleaning
- Exploratory Data Analysis]
- Data Visualization
- Descriptive and Inferential Statistics
- Outside Research]
- Conclusions and Recommendations

## Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|sat_participation|float|sat_2017_i, sat_2018_i|SAT participation rate for a particular state (1.0 means 100% of students in specified state participated in SAT|
|sat_read_write|int|sat_2017_i, sat_2018_i|Average SAT Evidence-Based Reading and Writing test score for a particular state (possible range from 200-800)|
|sat_math|int|sat_2017_i, sat_2018_i|Average SAT Math test score for a particular state (possible range from 200-800)|
|sat_total|int|sat_2017_i, sat_2018_i|Average SAT Total score for a particular state. The total score is the sum of the two individual tests ( Evidence-Based Reading and Writing, Math) (possible range from 400-1600)|
|act_participation|float|act_2017_i, act_2018_i|ACT participation rate for a particular state (1.0 means 100% of students in specified state participated in ACT|
|act_english|float|act_2017_i, act_2018_i|Average ACT English test score for a particular state (possible range from 1-24)|
|act_math|float|act_2017_i, act_2018_i|Average ACT Math test score for a particular state (possible range from 1-24)|
|act_reading|float|act_2017_i, act_2018_i|Average ACT Reading test score for a particular state (possible range from 1-24)|
|act_science|float|act_2017_i, act_2018_i|Average ACT Science test score for a particular state (possible range from 1-24)|
|act_composite|float|act_2017_i, act_2018_i|Average ACT composite for a particular state. ACT composite scores are calculated as the average of the 4 individual tests (English, Math, Reading, Science) (possible range from 1-24)| 
