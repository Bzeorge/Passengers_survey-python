# Airline Passengers Survey
In this project, I will explore the data about how were passengers satisfied with airline services. The data also contains informations about the flight(distance, duration, delay, etc).
<br>The dataset comes from kaggle.com and it is already divided into training and testing data. 


## About columns
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
<br>
<br>For this project I will need pandas - to work with database, numpy - to work data, seaborn and pyplot - to visualize the data and scikit learn to handle missing values.
<br>
<br>![02](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/29a2916d-d00f-4e30-be10-5d04165faa86)
<br>
<br> Test dataset has 25976 rows and 25columns. The train dataset has 103904 rows and 25 columns. Before any further analysis, I will merge both dataset together, to have more data and more accurate information, even though the train data contain enough records to complete the analysis.
<br>
<br>![03](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/526d3ae8-5976-4df4-957b-046bb0ddc972)
<br>![04](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/5bc86019-2427-436b-8c70-f2e4755ff83f)
<br>
<br> I´ve noticed that the first two columns are irrelevant so I will use drop function to remove them from the dataset. Also, the last column doesn´t start with a capital "S".
<br>
<br>![05](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/922cccd0-ce56-4176-a389-2e7159285955)
<br>![06](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/2c04cbdd-16b0-41a0-8c65-0c76648bae33)
<br>
<br>There are quite a big differences between mean and max values in three columns - Flight Distance, Departure Delay and Arrival Delay. There is a chance of outliers.
<br>
<br>![07](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/b6c871ca-12d2-4699-972c-cc70f5102705)
<br>![08](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/de5a08d1-41b5-4424-9dbc-6d12b76a57bf)
<br>![09](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/a9be4cc7-03fc-4f67-b399-0fc039daab8d)
<br>
<br>The column Arrival delas is the only column with a missing value. The amount of missing values is not statistically significant(393 out of 129.880) so I could simply drop the rows with missing values, but for further practice I will use Scikit Learn to fill in the missing values. I will use median because the column has a large max value which disproportionately increased the mean value. But to be sure I will use boxplot to visualize the data composition.
<br>
<br>![10](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/6bb85d98-e8d7-416c-aae9-832c3a6999ba)
<br>
<br>As you can see on the box plot there are some outliers
<br>
![11](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/3037532f-b8b6-4cc8-a703-054fb4b83d8b)
<br>
<br>The dataset in clear from duplicates.The box plot will help with detecting the outliers.
<br>
![12](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/a7d61c16-88da-4afb-bacd-fb376abda653)
<br>
<br>


### Plotting the data
<br>
<br>
![13](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/b3b0643c-2137-4d5f-8794-d6049a6fd07e)
![14](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/6dd902a3-13d6-474c-a0ea-e0d4531c7a7b)
![15](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/ddaf96e1-6b8f-485c-a0af-c57daad925bf)
![16](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/42cf22b5-76c8-4039-b25d-f868a62eebef)
![17](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/20e1a092-b5df-4ed8-8d63-a7976ccd7322)
![18](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/078d83ba-9ee3-43c4-b06c-6f3176014fdd)
<br>
<br>To make rating plots more clear I decided to cluster them into two categories - Before flight and During flight.
<br>
![19](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/0b828a27-1890-4460-8089-51e1db033d4d)
![20](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/6daaefa8-4785-444c-b9ec-d5f188a6f10a)
![21](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/a69df258-5369-499b-bbf9-495305a7b659)
<br>
<br>The last part will be to find out what affects the customers satisfaction the most - in other words, what has the strongest correlation with satisfaction. Because the data set contains several categorical variables, it is necessary to transform them into numerical variables first.
<br>
![22](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/b37f32a0-db84-40e1-b897-b22632f4c3be)
![23](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/d1de1d35-f562-440d-b544-fbcaeb1233bf)
<br>
<br>The dataset is now changed and contains only numerical values. This will help in the next step, which is to make a correlation matrix.
<br>
![24](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/3902bd61-09fa-4d2b-ab87-735d3c8e097e)
<br>
<br>For better visual, I will plot the correlation matrix as a heat map to see, between which columns is a strong correlation(positive or negative) 
<br>
![25](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/0740739f-d823-4e84-9ec6-f629a6412c8c)
<br>
<br>There is no significant correlation between Satisfaction and other columns. The strongest correlation in dataset is between Departure and Arrival delays because they follow each other.
<br>
<br>I will take a closer look at the relationship between Departure delay and customer Satisfaction. I created two categories for delay - Yes and No, and I set the limit for 15 minutes to filter out small delays.
![26](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/19d38783-ca68-46c0-859f-3ff88371a883)
![27](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/68a61225-ce62-4a47-9a9c-170739479d7b)
<br>
<br>There is 22% chance, that the airplane will have a delay larger than 15 minutes
<br>
![28](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/ebc93c8b-5491-4d87-828a-171c10115e96)
![29](https://github.com/Bzeorge/Passengers_survey-python/assets/74241688/2660b6b7-0c34-4f2b-b420-36cbe026eb0e)
<br>
<br>The delay has no significant effect on customer satisfaction.
<br>
<br>
### Conclusion
<br>
<br>Based on the survey, several facts can be stated:
<br>  -people on personal travel in Eco and EcoPlus class tend to be more likely dissatisfied
<br>  -gate location and inflight wifi services got the least amount of high rating
<br>  -the strongest correlation is between cleanliness and food and drink, seat comfort and inflight entertainment(even though these categories doesn´t relate to each other)
<br>  -overall people are more neutral or dissatisfied with the airline services




