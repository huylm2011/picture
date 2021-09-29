## Project 5: Data Visualization
##### Dataset: 201902_fordgobike_tripdata.csv



### Overview of the Data:
---
This dataset is about bicycle rides using a bike-sharing system. my target is to check the dataset information features and explore the relationship among many features in dataset.

---
##### Dataset inlcudes infomation about the duration of the customer and subscriber who use bike in Janury 2019, time trip they use bike and their gender,etc,..
---
##### With those infomation, i can find out many information about this dataset. For example: how long did they use bike for the trip? Which is the most age who use bike? Or which is the most gender ( male or female ) using bike for the trip? And In this project, i focus on 3 insights in question format to find out the thing i want:

#### Three main insights:
1.When are most trips taken in terms of time of day, day of the week, or month of the year?

2.Which day of the week has the most average trips duration?

3.Does the above depend on if a user is a subscriber or customer?


---
### A summary of main findings:

The first insights correspond to the univariate exploration:
- When are most trips taken in terms of time of day, day of the week, or month of the year?
---
To answer this question, i create a visualize to see the trip taken in terms of hour of day and weekday

---
Visualize Hour of Day


![image](https://user-images.githubusercontent.com/68053596/135077711-a7e09b2c-a019-4bea-904e-ae430ca62b3e.png)

So look at the visualize,I can see with 17 hours is the most significant times of Day(24h) with more than 20.000 trips.

---
Keep doing to answer weekday:

![image](https://user-images.githubusercontent.com/68053596/135077757-3614377c-0e6c-40f4-a589-a2e98949ef43.png)


##### We can see Thursday is the most days of the week with more than 30.000 trips in an easy way
---
---

The second insight correspond to Bivariate Exploration:
- Which day of the week has the most average trips duration?
---
To answer this question, icreate visualize to see the relationship between weekdays and duration: (becasue duration is the fields that describe the average time they use bike)
So i got the final infomation that Sunday and Saturday have the highest average of trip duration with more than 800 secs.

![image](https://user-images.githubusercontent.com/68053596/135077781-cf558ea5-7af1-41e2-95a6-122ecbdb38e3.png)



---

Finally, The third insight correspond to Multivariate Exploration
- Does the above depend on if a user is a subscriber or customer?
---
To answer this quesiton, the fields in dataset type_user is categorical type include Customer and Subscriber. So i add this field to see the change:

---

![image](https://user-images.githubusercontent.com/68053596/135077806-7b0140d6-2042-4d61-ba2d-ac20e97f0218.png)

The infomation i got is:
-  Customer is type of User have the most average trip duration on Sunday and Saturday
- Subcriber is type of User have lower average trip duration than Customer.

---
With the relationship between hour of day and duriation by Type of User:

i do the same thing

![image](https://user-images.githubusercontent.com/68053596/135077842-8f98079f-f97e-4435-8bc6-9356e906ac01.png)

And get 2 answers to know more about the final insights.
- Customer is type of User have the most average trip duration on day 3.
- Customer have higher average trip duration on all day than subscriber.

That's all my explanation about the dataset and its necessary for the explanatory presentation.

Thanks for reading.
