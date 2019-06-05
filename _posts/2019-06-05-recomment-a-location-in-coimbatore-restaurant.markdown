---
layout: post
title:  "Recommending a Location within Coimbatore City to open a Restaurant"
date:   2019-06-05 10:15:00 +0530
categories: jekyll update
---

## 1. Introduction:

### 1.1 Background :
      Opening a Restuarant and running it successfull, is not a simple endeavour. There are quite lot of things one have to brainstorm before opening a restaurant like target customers, frequency of the customers, parking facility, ambient environment, signature dishes, competitors,etc. It would be a business savy for restaurant owners to get places to open their restaurants which answers several questions like:
            a. Number of restaurants within 1000 meters from a place
            b. Type of restaurants within 1000 meters from a place
            c. Ratings and Reviews of restaurants
            d. What are the popular venues within 1000 meters from that place ?

### 1.2 Business Problem :
        This project aims to solve the following research question : "In Coimbatore City, if someone is looking to open a restaurant, where would we recommend that they open it?

### 1.3 Interest :
      Restaurant owners or Entrepreuners would be interested to get to know a likely place within Coimbatore City to open a restaurant.

## 2. Data

### 2.1 Data Sources :
      Targeting Coimbatore city, we will be requiring all the localities within Coimbaotore city. Hence I searched for pincode details of Coimbatore city, which helped me to land in the following page:

`https://www.mapsofindia.com/pincode/india/tamil-nadu/coimbatore/`

Scraped the webpage to get the table with features "Location", "Pincode", "State", "District" using BeautifulSoup and Python requests library.

Later, using geopy geocoders, generated Latitude and Longitude of the locations in that aforementioned table, which will be used to get the venues within 1000 meters or 2000 meters radius using FourSquare API.

In Particular, as we are only interested in "Restaurant" type venues, we will filter the "Restaurant" type venues from the dataframe.

Two data sources are used here:
	a. https://www.mapsofindia.com/pincode/india/tamil-nadu/coimbatore/
  b. FourSquare location data API


Example DataFrame from mapsofindia:

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f3.png)

Example DataFrame from geocoders:

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f2.png)

Example DataFrame from FourSquare API:

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f1.png)

### 2.2 Data Cleaning

	Initially “Coimbatore” pincodes were extracted as table using Beautiful Soup and Python requests library. Then, using geocoders, latitude and longitude coordinates have been found for all the locations in Coimbatore. But for some locations, latitude and longitude were not returned, for which I’ve inserted “NaN” values. In total 584 locations were there which later after removing “NaN” observations resulted in 224 locations.

Using FourSquare location data API, queried for venues within a radius of 2000 meters from the latitude and longitude of the locations. In total, 1938 rows of venues were returned for 224 locations by FourSquare API.

The head portion of the resulted dataframe is as follows:

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f4.png)

Totally 219 unique venue categories were there which includes but limited to 'Optical Shop', 'Bar' 'Bakery' 'Bus Station' "Men's Store"
 'Fast Food Restaurant' 'Hotel' 'Café' 'Lounge' 'Hyderabadi Restaurant'
 'Indian Restaurant' 'Multiplex' 'Science Museum' 'Scenic Lookout'
 'South Indian Restaurant' 'Bistro' 'Restaurant' 'Ice Cream Shop'
 'BBQ Joint' 'Vegetarian / Vegan Restaurant' 'Middle Eastern Restaurant'
 'Chaat Place' 'Chinese Restaurant' 'Performing Arts Venue' 'Lake'
 'Smoke Shop' 'Donut Shop' 'Hotel Bar' 'Stadium' 'Park' 'Pub' 'Coffee Shop'
 'Breakfast Spot' 'Garden' 'Bookstore' 'Pizza Place' 'Historic Site'
 'Food Court' 'Gaming Cafe' 'Mobile Phone Shop' 'Snack Place’, etc.
But as we are only interested in the “Restaurant” Venue type/category, those type of venues results alone filtered out from the data frame.
Calculated the frequency of common venues in each of the locations and the results were arranged in descending order based on the frequency of the venues.

Top 5 venues for each of the locations have been calculated.

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f5.png)

The top 5 venues for each of the location have been converted into a nice data frame filtered for only “Restaurants” data in it. After cleaning and ranking according to the frequency of the venues.

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f6.png)

## 3. Methodology
### 3.1 Machine Learnings
Using unsupervised algorithm, K-Means, clusters were formed and k value adjusted to 4.

### 3.2 Exploratory Analysis
Map with the clusters were plotted using folium.

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f7.png)

Most common venue (10 venues) have been derived out of the data. Individual clusters with the location venues have been reported.

### 3.3 Examine Clusters

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f8.png)

## 4. Results
Either the invester can choose location with lesser number of restaurants as there will not be any competitors or choose a location with more number of already established restaurants and offering the facilities or ambience which the old restaurants failed to accomplish. In that case, there are two types of results presented below.

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f9.png)

The data result for the same is as follows:

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f11.png)

Locations with least number of Restaurant venues:

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f10.png)

Locations where no restaurant venues are reported:

![](https://github.com/sathishnotes/Coursera_Capstone/raw/master/f12.png)

## 5. Discussion
There are many locations where Restaurant venue category was not reported as of FourSquare location data API. But I believe that, using Google places API and other API’s we can wrangle more Restaurant venue category data from those places. Doing analysis with more data would yield more accurate analysis I believe. Like I said before, an invester or business person or restaurant owner can take this data to see the current trend of the Restaurants in each of the locations within coimbatore as a continued analysis to improve his business and also they can use the data to open a restaurant in any of the reported places.
He can consider opening restaurant based on the following:
	a. Locations with more restaurants
	b. Locations with less restaurants
	c. Locations with no restaurants

## 6. Conclusion
As to conclude, I used FourSquare API to get the venues nearby the locations of Coimbatore within 2000 meters radius and upto 100 venues resulted in 1938 observations. Upon which, the K-means clustering algorithm was used to cluster the venues in each of the locations and analysed the individual clusters. Frequency for the occurence of the venue category “Restaurants” were filtered out and results were reported for three types of locations. Locations with more restaurants, locations with less number of restaurants, and locations with no restaurants. From which, An investor or restaurant owner or anyone who wants to open a restuarant in coimbatore can choose. It can be extended to look for the reviews and ratings for each of the restaurants reported and can be arranged based on the good reviews and ratings. We can also look for the nearby venues with colleges, IT offices and other workplaces or industries so as to think of regular crowd to the restaurant which is about to be opened.
