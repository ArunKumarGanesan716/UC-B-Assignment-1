# Will the Customer Accept the Coupon?

The analysis focuses on whether a driver would accept a coupon for

*   Bar
*   Coffee house
*   Carry away or take home
*   Restaurant less than 20 min Away
*   Restaurant 20 to 50 min away

The data set includes User information, Contextual information and Coupon attributes

Data: [DataSet](https://github.com/ArunKumarGanesan716/UC-B-Assignment-1/blob/main/data/coupons.csv)
File: [File](https://github.com/ArunKumarGanesan716/UC-B-Assignment-1/blob/main/CouponAcceptanceAnalysis.ipynb)

Few standout observations were

*   The were 6 columns what had null values on it

![Picture1](https://github.com/user-attachments/assets/f78d4dab-b8c0-41e5-a358-5ec9cff7dba4)

*   Of which the Car was the most significant with over 12576 - There cannot be any assumptions if the individual has a car and not and it was a statistically large number to ignore
*   I decided to remove that column from the data frame
*   Then I created a missing data heat map with the remaining columns

![Picture2](https://github.com/user-attachments/assets/9d4d31c5-bbec-47f6-912b-35d25582335e)

And noticed there were rows where all of the coupons was null, this value would skew the results and removed the rows which had all 5 as null and rechecked the heatmap to see if there were more overlaps

![Picture3](https://github.com/user-attachments/assets/7b68b363-2afa-483a-adec-57d7750f70e9)

This helped me arrive with a clean data frame.

*   The next check was to check for duplicated – there were about 74 duplicates - But looking at the data frame it is impossible to determine if these are duplicates since there are no unique identifiers. I decided to keep the duplicates
*   Some of the visualization for Coupon and Temperature

![Picture8](https://github.com/user-attachments/assets/8ba2ab88-70ad-4c4b-8b83-0aeb4d0eb2b3)
![Picture7](https://github.com/user-attachments/assets/1bf4afae-4813-4211-ba52-92777264087c)
![Picture6](https://github.com/user-attachments/assets/40e25b9e-c485-4647-9209-6399378f7254)
![Picture5](https://github.com/user-attachments/assets/51f9e4e6-e783-44d2-8b11-309ab3fea900)
![Picture4](https://github.com/user-attachments/assets/25c33eb0-1628-428e-a5e1-1a4134d8bbd3)

*   The next step was the bar analysis

Some of the findings were - less than 3 vs more acceptance ration

![Picture9](https://github.com/user-attachments/assets/17175867-470e-454a-bfea-8576a6aec984)

Age Based analysis

![Picture10](https://github.com/user-attachments/assets/4bfdb2ce-70f7-4af8-9442-613dffcdcd66)

Acceptance Rate based on multiple factors

![Picture11](https://github.com/user-attachments/assets/9e27ad77-51f1-4138-bd1e-77d657402a25)

Some of the findings from the above exercise

_\# hypothesis: Young and Middle-aged drivers who are not divorced and visit bars frequently with a low income are more likely to accept bar coupons_

_\# When they are not travelling with kids._

_#Few Observations from the above analysis:_

_\# Bar coupon acceptance is more when the temperature is mid-range around the 55ish degree._

_\# Bar coupon acceptance is more when there are no kids travelling with the driver._

_\# Bar coupon acceptance is more when the driver is not widowed. Showing the drivers are more sociable and like to travel with friends and family._

_\# Bar coupon acceptance is less than other coupons such as coffee house, carry out & away and restaurant under $20. Showing given a choice the driver would prefer to go to a cheap restaurant or coffee house or take out than a bar._

_\# Bar coupon acceptance tends to be a little more when the driver is not in the Farming Fishing & Forestry occupation._

_\# Bar Coupon acceptance is more when the driver is more budget conscious visiting cheap restaurants more than 4 times a month._

_\# 4 time a month also shows the driver is more sociable and likes to go out with friends and family._

_\# Bar Coupon acceptance is more when the diver income is low_

_\# The above analysis does not consider all the factors that can affect the coupon acceptance and would require more analysis to get a better understanding of the data and trends._

For the self-investigation focused on non-habitual data

non\_habbit\_data\_columns **\=** \['destination','passanger','time','expiration','weather', 'temperature', 'gender','coupon','has\_children','education','maritalStatus','age','direction\_same','direction\_opp','Y','income'\]

Did a break down of the individual attributes when accepted and rejected via a pie chart

![Picture13](https://github.com/user-attachments/assets/ee56f2be-6ee9-48ec-81a4-f9df1dcb84cc)
![Picture12](https://github.com/user-attachments/assets/ba7b6ea5-470d-4d81-bd1d-48fe9b9ba291)

There were some noticeable patterns

  # Coupon acceptance is more when the driver is traveling to less urgent places and we see more rejections when the drivers are heading home or to work

  # Coupon acceptance increases when the driver is with friends.

  # Coupon acceptance increases when the coupon expiration is more 1 day compared to 2h

  # Male drivers have higher acceptance to coupon then female drivers

  # Coupon acceptance is low when they driver have children which might hint at healthy food habits

  # Coupon acceptance is more when the drives has some college -  no degree and the rejection are more if the driver has Bachelor degree

  # Strangely coupon acceptance when traveling opposite direction is higher than traveling in the same direction

Then I build some facet charts

![Picture17](https://github.com/user-attachments/assets/4375b619-4d7f-40fb-a0bc-5fb702c03d67)
![Picture16](https://github.com/user-attachments/assets/5d93a48f-acf4-4e2a-9605-236fb396bc8e)
![Picture15](https://github.com/user-attachments/assets/ac6ae4b5-b611-4b90-818a-302fcdd5ee3a)
![Picture14](https://github.com/user-attachments/assets/b422a2ee-68f4-4d3e-81ae-83a8863443ae)

Note: The Plotly chats do not show up in GIT

From the chats above can see

_\# The male coupon acceptance rate is more across all temperature and weather conditions and coupon types._

_\# sunny days have higher acceptance rate than rainy days and snowy days._

_\# Carry out & Take away acceptance rate is more on snowy days when the temperature is around 30 degrees._

_\# Carry out & Take away acceptance rate is more on rainy days when the temperature is around 55 degrees._

_\# Coupon acceptance rate is generally more for Carry out & Take away in both male and female drivers._

_\# Sunny days have higher acceptance rate than rainy days and snowy days._

_\# On sunny day around 80 degrees the male driver to female drivers’ acceptance variance is low for all coupon types except for Bar coupon._

_\# Male driver to female driver acceptance variance is more for Bar coupon_

*   For the Final analysis focus on women with income more than 50K and with formal education and is not unemployed or retired
*   Had to do some data transformation on income age and plot a facet grid scatter plot

_Few Observations from the above analysis_

_\# for a women earning more than 50K with a degree and a job_

_\# Women drivers with bachelor’s degree are more likely to accept the coupon than other women drivers with a degree._

_\# Married partners are more likely to accept the coupon than single and unmarried partners._

_\# Interestingly the category did not have any divorced or widowed partners._

_\# Drivers with bachelor’s degree are more likely to accept a coupon_

_\# When income is mid 50k they coupon acceptance is more_

