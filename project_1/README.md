# Project 1: Standardized Testing, Statistical Summaries and Inference

### Overview

#### Problem Statement

To boost the state participation rate and increase the usage of SAT examination by understanding the correlations between participation rates, subject scoring and other current issues.

---

### Executive Summary

#### Business Overview and Process

The College Board is a not-for-profit organisation that aims to expand access to college education. The board is dedicated to promoting excellence and equity in education.

A record number of schools that have decided to accept all or most of their freshmen without requiring test results. Two Ivy League schools have also decided that some of their graduate school programs do not need a test score for admissions. 
In response to low participation rates, the College Board has been bidding for contracts with states to increase participation rates. SAT is now free for students in public schools in 10 states in the U.S.

---

### Datasets

#### Datasets given

SAT 2017/18 Participation, Component Scores

ACT 2017/18 Participation, Component Scores

#### Datasets researched/ Other qualitative sources

https://blog.prepscholar.com/which-states-require-the-act-full-list-and-advice
https://www.collegeraptor.com/getting-in/articles/act-sat/states-act-sat-given-free/
https://blog.prepscholar.com/which-states-require-the-sat
https://www.theatlantic.com/education/archive/2015/06/should-the-sat-be-part-of-school/395417/
https://www.chicagotribune.com/news/ct-illinois-chooses-sat-met-20160211-story.html
https://www.insidehighered.com/admissions/article/2019/09/24/minority-and-first-generation-sat-scores-fall-behind
https://www.dispatch.com/news/20170228/ohio-schools-must-now-give-act-or-sat-to-all-juniors
https://www.ppic.org/content/pubs/report/R_116HJ3R.pdf
https://hechingerreport.org/questioning-their-fairness-a-record-number-of-colleges-stop-requiring-the-sat-and-act/
https://www.kut.org/post/nations-population-growth-slows-texas-sees-jump
https://www.texastribune.org/2019/05/08/texas-keeps-growing-where-are-newest-transplants-coming/https://www.texastribune.org/2018/10/10/analysis-texas-school-finance-budget-lbb/

#### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**act_2017_participation**|*float*|ACT|Student participation in the standardised test by state| 
|**act_2017_english**|*float*|ACT|The average score obtained by students for the English segment by state, scored between 1 and 36|
|**act_2017_math**|*float*|ACT|The average score obtained by students for the Math segment by state, scored between 1 and 36|
|**act_2017_reading**|*float*|ACT|The average score obtained by students for the Reading segment by state, scored between 1 and 36|
|**act_2017_science**|*float*|ACT|The average score obtained by students for the Science segment by state, scored between 1 and 36|
|**act_2017_composite**|*float*|ACT|The average composite score obtained by students in the state, scored between 1 and 36|

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**sat_2017_participation**|*float*|SAT|Student participation in the standardised test by state| 
|**sat_2017_evidence-based_reading_and_writing**|*integer*|SAT|The average score obtained by students for reading and writing by state|
|**sat_2017_math**|*integer*|SAT|The average score obtained by students for the Math segment by state|
|**sat_2017_total**|*integer*|SAT|The average total score obtained by students in the state|

---

### Summary Statistics

#### Participation Rates

Answers for highest and lowest participation rates:

2017 SAT:
* Highest: District of Columbia, Michigan, Connecticut, Delaware, New Hampshire
* Lowest: North Dakota, Mississippi, Iowa, Missouri, Utah

2018 SAT:
* Highest: Colorado, Connecticut, Delaware, Michigan, Idaho
* Lowest: North Dakota, Wyoming, South Dakota, Nebraska, Wisconsin

2017 ACT:
* Highest: Alabama, Kentucky, Wisconsin, Utah, Tennessee
* Lowest: Maine, New Hampshire, Delaware, Rhode Island, Pennsylvania 

2018 ACT:
* Highest: Alabama, Kentucky, Wisconsin, Utah, Tennessee
* Lowest: Maine, Rhode Island, New Hampshire, Delaware, Pennsylvania

#### Relationship between SAT Scores and Participation Rates 2017 and 2018:

Both scores show a negative correlation with the SAT participation rate in 2017 and 2018. This indicates that the higher the participation rates by states result the lower the scores.

#### Central Tendency, Spread, Skew SAT 2017 and 2018:

|Feature|Mean|Median|Std|Skew|
|---|---|---|---|---|
|**2017 Participation**|0.398|0.380|0.352|0.346|
|**2017 Evidence-based Reading and Writing**|569.1|559.0|45.67|0.273| 
|**2017 Math**|556.9|548.0|47.12|0.365| 
|**2017 Total**|1126.1|1107.0|92.49|0.311|  
|**2018 Participation**|0.457|0.520|0.373|0.136|
|**2018 Evidence-based Reading and Writing**|563.7|552.0|47.50|0.282| 
|**2018 Math**|556.2|544.0|47.77|0.530| 
|**2018 Total**|1120.0|1098.0|94.16|0.466|  

#### Shapiro-Wilk Test (Test for Normality):

**At the 5% level of significance:**

- ACT and SAT Math scores are not normally distributed.
- 2018 ACT and 2017 and 2018 SAT Reading scores are not normally distributed. However, we cannot reject the null hypothesis that the 2017 ACT Reading follows a normal distribution. 
- ACT and SAT participation rates are not normally distributed.

#### Issues on data granularity, aggregation and population sizes and rates:

Granularity and aggregation:

The granularity of data refers to the size in which data fields are sub-divided. In this case, there is coarse granularity in terms of recording of participation rates by states. The 2017 participation rates show humps, which indicate that there could be composite distributions in each field. Even though the granularity of the participation rates is coarse, the rates are greatly influenced by state requirements and whether the tests are administered for free. For instance, 12 states in the U.S. require ACT. So, conducting a statistical inference using these data still makes sense. In order to draw more inference, we could aggregate more data on the income, race, gender and school assessment scores to identify the groups of students who would sit for a particular tests.


Population sizes and rates:

The data provides participation rate by state. Different states have different population sizes, which could mean that a state with a bigger population size but smaller participation rate will still have a higher absolute number of students taking a test. This means that the participation rate may not reflect the true popularity of the tests nationwide. The rates could be weighted to reflect the population size or the absolute number of students who sat for a test could be used instead. 

#### Appropriateness in comparing specific SAT and ACT Math Scores:

The SAT and ACT math scores are not normally distributed. So it is not possible to compare the two scores which could possibly have been done if they had been normally distributed. 

Given the current data, we have two sets of tests with different scoring requirements and different scales of scoring. Besides, we have seen that states with lower participation rates tend to have higher scores. Since SAT have lower participation rates in general, it would mean that the students would have higher scores. This is because of self-selection, whereby only higher-performing students will take an additional test on top of the one required by the state since they are able to do well on the test. Thus, it is not appropriate to compare SAT and ACT math scores.

---

### Outside Research

Findings:

Colorado:

In 2017/18, Colorado became one of the 10 states to cover the cost of the SAT for all their public school students. The College Board has been pushing hard to win contracts with entire states or districts. ACT, on the other hand lost contracts in Colorado, contributing to the big drop in participation from 100% to 30%.

Illinois:

Illinois was also one of the 10 states to start providing SAT for free for students. ACT also lost its contract with Illinois. Performance-wise, Illinois lagged behind national mean scores  in 2018 in the SAT but the ACT scores rose and the average composite score was higher than the national average. This can again be attributed to student self-selection to ACT. Since SAT is now provided for free, most students will sit for the test but only the better students will sit for both ACT and SAT. 

Ohio: 

Both the SAT or ACT is given during the school day and both tests are administered for free because the state is paying for each student to take one of the tests once. The ACT is the overwhelming preference of students in Ohio even though Ohio accepts both ACT or SAT as the requirement for high school test. Each school district selects whether the free test will be ACT or SAT. The ACT has traditionally been the more popular test in the Midwest, which is where Ohio is located. This could be the reason why ACT is still the more popular test despite SAT's restructuring of scoring methodology in 2015.

---

### Conclusions and Recommendations

Based on data exploration and other events, the most effective way for the College Board to increase the SAT participation rate is to convince state lawmakers for them to fund the test for students and to make it a requirement for graduation.

The state chosen is Texas because of:
1. Participation rate, population size and projected growth in population: 62% participation rate in the second most populus in the U.S. gives enough room for expansion of the SAT. Texas saw the biggest increase in population in 2018. What is notable is that Texas population saw a jump as the nation's population growth slows, making it an ideal state for the SAT to gain a foothold in.
2. Make-up of Texas' population: In 2018, the majority of migrants to Texas came from other countries rather than other states in the US or Latin America. The College Board introduced fee waivers and free test preparation in an attempt to increase access to the test for low-income, first-generation and minority students. This can be utilised well in Texas.
3. Current participation rate an indication of ease of legislating SAT in the state: The 2018 SAT participation rate was 66% while the ACT participation rate was 41%, indicating that standardised tests are common in the state. This would make it easier for the state to buy in to the idea of mandatory testing.

Recommendations for Texas:
1. Requiring students to take SAT for graduation and making it a state-funded test is the most effective way of increasing state participation rate. 
2. It is also important to highlight the fee waivers and free test preparation that have been introduced by the College Board to appeal to the state and the minority students.
3. The College Board can emphasise that the test has been redesigned and encourage test preparation in order for students to score better should the state have to justify funding of the SAT using test scores. 

Additional data required for a more informed investigation:

1. The result of a bill now making its way through California's legislature requiring the public University of California system and California State University system to study the usefulness and fairness of standardised tests in the admissions process. This may have an impact on state funding of standardised tests nationwide. 
2. The number or percentage of universities in Texas that require or recommend SAT testing. This assumes that most Texan students pursue their college education in Texas itself.
3. The size of student population not taking either tests to investigate the possible increase in SAT test administration. 
4. Possible correlation of test scores with ease of getting state funding. If the chances of obtaining the funding is justified via higher test scores, then the College Board should highlight the availability of test preparations for SAT now that it has been redesigned to be aligned with Common Core standards. 
5. State budget for education: Texas has to keep the state and local shares at about 45 percent each, which means that the lawmakers have to find 9 billion dollars for the next two-year budget. Whether they are able to obtain the 9 billion dollars will impact whether state funding can be implemented for SAT. 
---
