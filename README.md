# AIML-Mod-5-Practical-App-1

## Problem Statement
Based in the data collected for different demographic groups, their behavior on going to bars and restaurants, coupon type, other factors and their response to accepting coupons for bars and restaurants that were delivered on the drivers’ cell phone, predict the likelihood of a driver accepting a coupon.

## Goal
Use the knowledge and techniques acquired so far from the course to distinguish between customers who accepted a driving coupon versus those that did not.

## Data
Use the link to the [Coupons Dataset](https://github.com/deepaksil/AIML-Mod-5-Practical-App-1/tree/main/data)

Source: [UCI Machine Learning repository](https://archive.ics.uci.edu/dataset/603/in+vehicle+coupon+recommendation) and was collected via a survey on Amazon Mechanical Turk. 

Data Description: User attributes, Contextual Attributes, and Coupon Attributes are available in the Jupyter Notebook

## Solution
Use the link to the [Jupyter Notebook](https://github.com/deepaksil/AIML-Mod-5-Practical-App-1/blob/main/AIML_MOD5_PA1.ipynb)

## Findings
  ### Data Quality & Data Scrub
* Car Column: Dropped since the missing percentage is very high (over 99%)
* Bar, CofffeeHouse, CarryWay, RestaurantLessThan20, Restaurant20To50 Columns
  * Replace 1~3, 4~8 with 2 and 6 respectively (mid points)
  * Replace ‘never’ and ‘less1’ with 0
  * Replace gr8 with 8
  * populate NaNs with the median
  * change the datatype to numeric
* Age - replace 50plus with 51 and below21 with 20; change the datatype to numeric
* Income - parsed the data as income_low and income_high without the dollar and dash signs and stored them into two new columns
* Recommendations:
  * Rename the column names to all-lower cases
  * Where possible, change the data and data types to numeric type from alpha-numeric for ease of comparison and perform any mathematical operation or numeric comparison.  E.g., temperature, expiration, etc.

### Bar Coupons
* The overall acceptance rate for all coupon types is 0.57. Whereas, for Bar coupon it is 0.41 which is less than the overall rate.
* Drivers who went to bars more than 3 times a month are more likely to accept bar coupons (0.77) than the driver who goes less frequently (.37).
* Young drivers (age less than 25) and who visited bar more than once a month are much more likely to accept the bar coupon than the rest of the other drivers, 0.70 vs 0.34
* Drivers who went to bar at least once a month, did not have kids as passengers, and occupation other than Farming Fishing & Forestry had the acceptance of 0.72, whereas all other drivers had an acceptance rate of 0.38.
* Acceptance Rate of drivers who go more than once to a bar, with passengers that were not kids, and not widowed had similar acceptance rate compared to the drivers who go more than once a month to the bar and under the age to 30 (0.7172 vs 0.7217).
* The drivers who went to cheap restaurants more than four times a month and earn less than 50K was low (0.4535) that clear indicates income plays a critical role.

### Independent Investigation - 'Carry out & Take away' Coupons
* As is evident from the histogram, the acceptance rate of Carry Out & Take Away Coupons are very similar across each Marital Status Group, with Widowed Group higher than the rest.
* The other groups (other than widowed) have acceptance rate close to the overall acceptance rate of 74%
* Widowed data size of 26 is significantly smaller than the others, so significant conclusion on the acceptance rate may not be made.
* Among the married couples, coupons sent to male divers has higher acceptance rate than to the female drivers (75% vs 72%)
* Driving Direction has no significant effect on the acceptance rate for Married Couples
* **Recommendations:**
  * Since the criteria chosen for this analysis were limited and did not show significant variation in acceptance rates, it is recommended that other features are investigated.
  * Some suggested criteria to consider:  drivers with children (e.g., if the coupon is based on order size), time of day (e.g., more carry-out may happen in the evening), drivers' income (low income may mean less purchase, high income may mean going to expensive restaurants).
