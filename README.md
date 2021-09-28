## Project 5: Data Visualization
##### Dataset: 201902_fordgobike_tripdata.csv
###### This dataset is about bicycle rides using a bike-sharing system. my target is to check the dataset information features and explore the relationship among many features in dataset.


## Describe details:
---
First table, i import all library that needed for all project and load file csv below:


``` python
    # import all packages and set plots to be embedded inline
    import numpy as np
    import pandas as pd
    import matplotlib.pyplot as plt
    import seaborn as sb
    %matplotlib inline
    
    df = pd.read_csv(r'E:\Project_5\201902_fordgobike_tripdata.csv')
```
---
After that, i start to view data and start to clean data by remove duplicate and null data, change datatype column by using function:
```python
    #check duplicate record
    df.duplicated().sum()

    #check null values
    df.isna().sum()
    
    #drop null values
    df.dropna(inplace=True)

    #convert member_birth_year from float to int
    df.member_birth_year = df.member_birth_year.astype(int)
```
---
I check data again by using some functions: 
```python
    df.info()
    df.describe()
    df.head()
```
---
Then, data is clean. I created a copy dataframe by *copy* function in order not to affect in raw dataframe:

``` python
    #create a df_copy to change data frame
    df_copy = df.copy(deep=True)
```
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

``` python
#Take the time from start time to see the detail and answer the first insight question
#Take hour from start_time
df_copy['start_hour'] = df_copy['start_time'].dt.hour
#Take week_day from start_time
df_copy['start_day'] = df_copy['start_time'].dt.day_name()
#Take month from start_time
df_copy['start_month'] = df_copy['start_time'].dt.to_period('M')

```
---
Then, i create visualization to see hour of day by using countplot:

```python
#count hour and order hour from max to min
hour_counts = df_copy['start_hour'].value_counts()
hour_order = hour_counts.index

base_color = sb.color_palette()[0]
plt.figure(figsize=(14,10))
plt.title('Trips taken in terms of Hour of Day',fontsize=20)
sb.countplot(data = df_copy, x='start_hour',color = base_color,order = hour_order)
plt.ylabel('Count of trips', fontsize=14)
plt.xlabel('Hours of Day (24h)',fontsize=14)

```
---
Visualize i create:


![image](https://user-images.githubusercontent.com/68053596/135077711-a7e09b2c-a019-4bea-904e-ae430ca62b3e.png)

### Conlusion:

**We can see with 17 hours is the most significant times of Day(24h) with more than 20.000 trips.**

---
After that, i create visualize to see weekdays by using countplot:

```python
#count Weekday and order weekday from max to min
day_counts = df_copy['start_day'].value_counts()
day_order = day_counts.index

base_color = sb.color_palette()[0]
plt.figure(figsize=(14,10))
plt.title('Trips taken in terms of Weekdays',fontsize=20)
sb.countplot(data = df_copy, x='start_day',color = base_color,order = day_order)
plt.ylabel('Count of trips', fontsize=14)
plt.xlabel('Weekday',fontsize=14)
```
---
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

``` python
base_color = sb.color_palette()[0]
plt.figure(figsize=(14,10))
plt.title('Trips taken in terms of Weekdays and Duration(s)',fontsize=20)
sb.barplot(data=df_copy, x= 'start_day', y='duration_sec',color = base_color);
plt.ylabel('Duration by secs', fontsize=14)
plt.xlabel('Weekdays',fontsize=14)
```
---
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
```python
plt.figure(figsize=(14,10))
sb.barplot(x= df_copy.start_day, y= df_copy.duration_sec, hue=df_copy.user_type)
plt.ylabel('Duration by secs', fontsize=14)
plt.xlabel('Weekdays',fontsize=14)
plt.title('Trips taken in terms of Weekdays and Duration(s) by Type of User',fontsize=20)
plt.legend(title='Type of User')
```
---
Visualize i create:

![image](https://user-images.githubusercontent.com/68053596/135077806-7b0140d6-2042-4d61-ba2d-ac20e97f0218.png)


### Conlusion:
-  Customer is type of User have the most average trip duration on Sunday and Saturday
- Subcriber is type of User have lower average trip duration than Customer.

---
Second, I create visualize to see the relationship between hour of day and duriation by Type of User:

```python
ase_color = sb.color_palette()[0]
plt.figure(figsize=(14,10))
plt.title('Trips taken in terms of Hour of Day and Duration(s) by Type of User',fontsize=20)
sb.barplot(x= df_copy.start_hour, y= df_copy.duration_sec, hue=df_copy.user_typeConclusion)
plt.ylabel('Duration by sec', fontsize=14)
plt.xlabel('Hours of Day (24h)',fontsize=14)
plt.legend(title='Type of User')
```
---
Visualize i create:

![image](https://user-images.githubusercontent.com/68053596/135077842-8f98079f-f97e-4435-8bc6-9356e906ac01.png)

### Conlusion:
- Customer is type of User have the most average trip duration on day 3.
- Customer have higher average trip duration on all day than subscriber.


