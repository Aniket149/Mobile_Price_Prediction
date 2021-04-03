# Mobile Price Prediction: Overview

* Created mobile price prediction model which predicted mobile price. which may help consumer to set their budget for buying mobiles.
* Scraped flipkart mobile pages using python and Beautiful soup.
* Performing exploratory data analysis to find out relationship of price with other variable.
* Made linear regression model to predict mobile price.

# Code and Resource used
* Python version: 3.8.3
* Packages: pandas,numpy,sklearn,matplotlib,seaborn,beautifulsoup
* Scraped website: https://www.flipkart.com/search?q=mobiles&sid=tyy%2C4io&as=on&as-show=on&otracker=AS_QueryStore_OrganicAutoSuggest_1_5_na_na_na&otracker1=AS_QueryStore_OrganicAutoSuggest_1_5_na_na_na&as-pos=1&as-type=HISTORY&suggestionId=mobiles%7CMobiles&requestId=29410e87-cffb-4de1-8c08-dedf59dd28d8

# Web Scraping
Scraped flipkart website 'mobile' pages. we get 1340 mobiles data. with each mobile, we got the following:
* Mobile Brand
* Mobile Color
* RAM
* Storage
* Mobile display in cm
* Mobile display in inch
* Front Camera
* Back Camera
* Battery
* Battery Types
* Rating
* Price

# Data Cleaning
After scraping websites, we need to clean data so that we can analyze and make model. I made following changes:
* Splitting mobile brand and mobile color from description column and made new column each.
* Splitting RAM and Storage(ROM) from RAM column and made separate column for storage. These are ordinal variable we would convert them into numbers.
* Splitting Mobile display in cm and Mobile display in inch from display column and made separate column each. These are ordinal variable we would convert them into numbers.
* Splitting front camera and back camera from camera column and made separate column for front camera. These are ordinal variable we would convert them into numbers.
* splitting battery type from battery column and made separate column for battery type. These are ordinal variable we would convert them into numbers.
* Removing ₹ symbol from price column. change data type of price column(object to int).

# EDA
I looked at distribution of categorical variable and made pair plot of numerical variable to see relationship between them.
We observed that price has strong positive correlation with RAM, Storage and Front Camera. we will take RAM, storage and front camera for model building.
![mobile_price_by_brands](https://user-images.githubusercontent.com/72646092/113482437-65f13080-94bc-11eb-9408-61dd8d21d91b.jpg)
![mobile_price_by_color](https://user-images.githubusercontent.com/72646092/113482451-76a1a680-94bc-11eb-9dc6-2171132f9e32.jpg)
![mobile_storage_price_relationship](https://user-images.githubusercontent.com/72646092/113482465-81f4d200-94bc-11eb-876d-4b79ad9d766b.jpg)
![mobile_front_camera_price_relationship](https://user-images.githubusercontent.com/72646092/113482478-8caf6700-94bc-11eb-8e29-a4c6c2eb3062.jpg)

# Model Building
We have observed linear relationship of price with RAM, Storage and Front Camera. We will take it for model building.
we would build linear regression model which would predict mobile price.
Prediction equation of the model:
#### Price = 980.53 * RAM + 1560.01 * Storage + 2171.76 * Front_Camera + 5016.43

# Model Performance
* Accuracy of the model: Score = 0.8787(87.87%)
