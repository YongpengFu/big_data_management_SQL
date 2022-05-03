# big_data_management_SQL
## Using Python to automate tasks from relational database

## Life Expectancy Around the World
### Introduction
#### Yongpeng Fu, Jacques Botha, Somnath Bhattacharjee
The subject matter of our group project is “life expectancy.”  Life expectancy can be defined as “the average age that members of a particular population group will be when they die” [1]. This is an interesting subject to us and to many others for a multitude of reasons. Life expectancy is considered a key metric that is commonly used in assessing the health of a population, it can vary significantly from one population to the next, it has doubled over the last century [2] and there are numerous factors that influence it.

Our group hopes to answer the following primary guiding questions.
* How has the life expectancy changed globally over time?
* What is the years lived with disability vs. Health expenditure per capita?
* What sort of relationship exists between Life Expectancy and GDP per capita?
* What sort of relationship exists between Life Expectancy and Healthcare expenditure per capita?
* Which factor, GDP per capita or Healthcare expenditure per capita appears to have a stronger relationship with Life Exepctancy?
* How gender gap life expectancy varies between Men and Women in US and Canada?
* What is the change in gender survival rates year-to-year in Canada?
* What is the average survival rates before and after 2000 for Men and Women in US and Canada?
* For which years was the death count at its maximum in US and Canada for the age groups under 5 and age 5 to 14?


We believe our guiding questions are those that are of interest to not only us but to many others. The answers to these questions may be able to provide some valuable insights as towards how people should choose to live their lives if they were to try to maximize their life expectancy. Understanding how your life choices with respect to where a person chooses to live, what a person chooses to consume, how a person chooses to utilize modern medicine or technology etc. These are all factors that we expect to play a significant role in shaping a populations life expectancy.

## DataSet

Our datasets were mainly obtained from Our World in Data [3]. Our World in Data is a scientific online publication that focuses on large global problems such as poverty, disease, hunger, climate change or even war. This is a very trustworthy place to pull the data from because its publications have been cited by renowned academic scientific journals, The Washington Post, The New York Times, and The Economist. For our project, we are using their data source because it provides a big picture for the life expectancy change around the world. All the data sets obtained from Our World in Data are completely open access under the Creative Commons BY license [4]. Under this license, the data provider grants us permission to copy, modify and publish the information for our course project.
 
Most of the datasets we gathered are organized in a tabular format unless otherwise indicated. The main csv table we will be using is named “life-expectancy.csv”. The table has 4 features including `Entity`, `Code`, `Year`, and `Life expectancy`, with 19209 records. The Entity and associated Code, on the country-, regional- and global-level, are entries for the record. The year feature has a time span from 1543 to 2019, which in combination with Code are important keys for us to join with other tables. The life expectancy at birth is of particular interest to us, which is described as the average number of years that a newborn could expect to live if he or she were to pass through life subject to the age-specific mortality rates of a given period. The whole dataset was compiled based on different sources [5-6]. And the total size of this table is about 500kb. Moreover, additional tables and their dominated features were used to answer particular guiding questions as follows:
* healthy-life-expectancy-and-years-lived-with-disability  

    1. `Healthy Life Expectancy`, 
    2. `Years Lived With Disability`: Average life expectancy of an individual born in a given year, disaggregated into the expected number of healthy years, and the number lived with disability or disease burden.


* years-lived-with-disability-vs-health-expenditure-per-capita

    3. `Health expenditure per capita`, PPP (constant 2011 international $): Total health expenditure is the sum of public and private health expenditures as a ratio of total population. It covers the provision of health services (preventive and curative), family planning activities, nutrition activities, and emergency aid designated for health but does not include provision of water and sanitation. Data are in international dollars converted using 2011 purchasing power parity (PPP) rates.
    
    
* life-expectancy-vs-gdp-per-capita

    4. `GDP PER CAPITAL`: The collected data was first published by Bolt, Jutta and Jan Luiten van Zanden in 2020 [7]. The listed world economy is based on Maddison style estimates, whose Project Database is based on the work of many researchers that have produced estimates of economic growth for individual countries.



* life-expectancy-vs-healthcare-expenditure

    5. `Health expenditure per capita`, PPP (constant 2011 international $): the same as in the years-lived-with-disability-vs-health-expenditure-per-capita table.
    
    
*  men-survival-to-age-65

    6. `Survival to age 65, male` (% of cohort): Survival to age 65 refers to the percentage of a cohort of newborn infants that would survive to age 65, if subject to age specific mortality rates of the specified year.


* women-survival-to-age-65

    7. `Survival to age 65, female` (% of cohort): Survival to age 65 refers to the percentage of a cohort of newborn infants that would survive to age 65, if subject to age specific mortality rates of the specified year.
    
    
* number-of-deaths-by-age-group

    8. breakdown of deaths by `age bracket`.
  
  
* median-age

    9. `Median_Age_2017`: Median age of the population. Historical estimates until 2015. UN Population Division, World Population Prospects, 2017 Revision. The median age divides the population into two parts of equal size; that is, there are as many people with ages above the median age as there are with ages below.
    
    
* number-of-deaths-by-risk-factor

    10. Study on the `causes of death` that has been publushed in the medical journal, the Lancet. This dataset gives estimates of the annual number of deaths for various causes such as high blood pressure, dierary choices such as alcohol consumptions and others. The total number of deaths encompases both male and female for all ages.
