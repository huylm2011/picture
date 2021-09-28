## Project 5: Data Visualization
##### Dataset: 201902_fordgobike_tripdata.csv
###### This dataset is about bicycle rides using a bike-sharing system. my target is to check the dataset information features and explore the relationship among many features in dataset.


## Describe details:
---
First table, i import all library that needed for all project and load file csv

---
##### After that, i start to view data and start to clean data by remove duplicate and null data, change datatype column by using: function:duplicated(),isna().sum(),df.dropna(inplace=True),astype(int)
---
##### I check data again by using some functions: info(), describe(), head()
---
##### Then, data is clean. I created a copy dataframe by *copy* function in order not to affect in raw dataframe: .copy(deep=True)
---
#### I have 3 insights in question format need to answer by using visualization:
1.When are most trips taken in terms of time of day, day of the week, or month of the year?

2.Which day of the week has the most average trips duration?

3.Does the above depend on if a user is a subscriber or customer?


---
#### Univariate Exploration
Univariate Exploration correspond to the first question: 

- When are most trips taken in terms of time of day, day of the week, or month of the year?
---
I start with exploration mentioned above because i want to know how the trips change through time.Firstly, I start with start_time ( Hour, Day and Month) by dividing into 3 columns: start_hour, start_day, start_month:

Then, i create visualization to see hour of day by using countplot:

---
Visualize i create:


![image](https://user-images.githubusercontent.com/68053596/135077711-a7e09b2c-a019-4bea-904e-ae430ca62b3e.png)

### Conlusion:

**We can see with 17 hours is the most significant times of Day(24h) with more than 20.000 trips.**

---
After that, i create visualize to see weekdays by using countplot:

Visualize i create:


![image](https://user-images.githubusercontent.com/68053596/135077757-3614377c-0e6c-40f4-a589-a2e98949ef43.png)


### Conlusion:

**Thursday is the most days of the week with more than 30.000 trips.**

---
---
#### Bivariate Exploration
Bivariate Exploration correspond to the second question: 

- Which day of the week has the most average trips duration?
---
I create visualize to see the relationship between weekdays and duriation:

Visualize i create:


![image](https://user-images.githubusercontent.com/68053596/135077781-cf558ea5-7af1-41e2-95a6-122ecbdb38e3.png)


### Conlusion:

**We can see Sunday and Saturday have the highest average of trip duration with more than 800 secs.**

---
#### Multivariate Exploration
Multivariate Exploration correspond to the third question: 

- Does the above depend on if a user is a subscriber or customer?

---
First, I create visualize to see the relationship between weekdays and duriation by Type of User:

---
Visualize i create:

![image](https://user-images.githubusercontent.com/68053596/135077806-7b0140d6-2042-4d61-ba2d-ac20e97f0218.png)


### Conlusion:
-  Customer is type of User have the most average trip duration on Sunday and Saturday
- Subcriber is type of User have lower average trip duration than Customer.

---
Second, I create visualize to see the relationship between hour of day and duriation by Type of User:

Visualize i create:

![image](https://user-images.githubusercontent.com/68053596/135077842-8f98079f-f97e-4435-8bc6-9356e906ac01.png)

### Conlusion:
- Customer is type of User have the most average trip duration on day 3.
- Customer have higher average trip duration on all day than subscriber.
