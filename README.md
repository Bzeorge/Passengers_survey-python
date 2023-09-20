# Airline Passengers Survey
In this project, I will explore the data about how were passengers satisfied with airline services. The data also contains informations about the flight(distance, duration, delay, etc).
<br>The dataset comes from kaggle.com and it is already divided into training and testing data. 


## Content
Gender: Gender of the passengers (Female, Male)
<br>Customer Type: The customer type (Loyal customer, disloyal customer)
<br>Age: The actual age of the passengers
<br>Type of Travel: Purpose of the flight of the passengers (Personal Travel, Business Travel)
<br>Class: Travel class in the plane of the passengers (Business, Eco, Eco Plus)
<br>Flight distance: The flight distance of this journey
<br>Inflight wifi service: Satisfaction level of the inflight wifi service (0:Not Applicable;1-5)
<br>Departure/Arrival time convenient: Satisfaction level of Departure/Arrival time convenient
<br>Ease of Online booking: Satisfaction level of online booking
<br>Gate location: Satisfaction level of Gate location
<br>Food and drink: Satisfaction level of Food and drink
<br>Online boarding: Satisfaction level of online boarding
<br>Seat comfort: Satisfaction level of Seat comfort
<br>Inflight entertainment: Satisfaction level of inflight entertainment
<br>On-board service: Satisfaction level of On-board service
<br>Leg room service: Satisfaction level of Leg room service
<br>Baggage handling: Satisfaction level of baggage handling
<br>Check-in service: Satisfaction level of Check-in service
<br>Inflight service: Satisfaction level of inflight service
<br>Cleanliness: Satisfaction level of Cleanliness
<br>Departure Delay in Minutes: Minutes delayed when departure
<br>Arrival Delay in Minutes: Minutes delayed when Arrival
<br>Satisfaction: Airline satisfaction level(Satisfaction, neutral or dissatisfaction)



## Main questions:
**1)How are passengers satisfied with airline services?**
<br>**2)What effects the satisfaction the most?**


### Exploratory data analysis
![01](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/82932f5e-eb39-4048-b08f-178f95803135)
<br>For this project I will need pandas - to work with database, numpy - to work data, seaborn and pyplot - to visualize the data and scikit learn to handle missing values.
<br>![02](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/29a2916d-d00f-4e30-be10-5d04165faa86)
<br> Test dataset has 25976 rows and 25columns. The train dataset has 103904 rows and 25 columns. Before any further analysis, I will merge both dataset together, to have more data and more accurate information, even though the train data contain enough records to complete the analysis.
<br>![03](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/526d3ae8-5976-4df4-957b-046bb0ddc972)
<br>![04](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/5bc86019-2427-436b-8c70-f2e4755ff83f)
<br> I´ve noticed that the first two columns are irrelevant so I will use drop function to remove them from the dataset. Also, the last column doesn´t start with a capital "S".
<br>![05](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/922cccd0-ce56-4176-a389-2e7159285955)
<br>![06](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/2c04cbdd-16b0-41a0-8c65-0c76648bae33)
<br>There are quite a big differences between mean and max values in three columns - Flight Distance, Departure Delay and Arrival Delay. There is a chance of outliers.
<br>![07](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/b6c871ca-12d2-4699-972c-cc70f5102705)
<br>![08](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/de5a08d1-41b5-4424-9dbc-6d12b76a57bf)
<br>![09](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/a9be4cc7-03fc-4f67-b399-0fc039daab8d)
<br>The column Arrival delas is the only column with a missing value. The amount of missing values is not statistically significant(393 out of 129.880) so I could simply drop the rows with missing values, but for further practice I will use Scikit Learn to fill in the missing values. I will use median because the column has a large max value which disproportionately increased the mean value. But to be sure I will use boxplot to visualize the data composition.
<br>![10](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/6bb85d98-e8d7-416c-aae9-832c3a6999ba)
<br>As you can see on the box plot there are some outliers
