# Battle of the Neighboroods - REPORT

## INTRODUCTION
Some of my friends are planning a visit to Connaught Place, New Delhi for an official meeting. They would surely want to stay in a hotel and would like to dine in a fancy restaurant. They also wish to ease up a bit by having some drinks. Since, they would be on a tight schedule, they would want to spend the least of their time on commute. So, we need to figure out the best combination of hotel, restaurant and bar, that we can suggest to them. I would like to propose them the best place to stay according to the choices.

## DATA SECTION
I would use the Foursquare API to retrieve all the information about hotels, restaurants and bars in Connaught Place, New Delhi. All the venues retrieved in the place would have latitude and longitude. That information will be used to plot the venues on a map using Folium. Venue id of a venue could be used to retrieve rating of a venue.

## METHODOLOGY
What basically will be done in this project is that, we wil gather the details of hotels, bars and restaurants. With the latitude and longitude data, we will mark the venues on the map according to their coordinates. First we query the details of Restaurants in the location. Next, we repeat the same process for bars and hotels. 
We can retrieve the data with the following url :-
```
query = 'Restaurant'
url = 'https://api.foursquare.com/v2/venues/search?&client_id={}&client_secret={}&v={}&query={}&ll={},{}&radius={}&limit={}'.format(
    CLIENT_ID, 
    CLIENT_SECRET, 
    VERSION,
    query,
    latitude, 
    longitude, 
    radius, 
    LIMIT)
```
We only need to change the variable query. We have already defined the variables elsewhere in the code. 

###### Data Cleaning :-
We will store the retrieved information in a dataframe. Our dataframe would look something like this :-
https://github.com/DivS13/Coursera_Capstone/blob/master/Images/Data1.JPG

We clean the data and turn it into the following dataframe :-
https://github.com/DivS13/Coursera_Capstone/blob/master/Images/Data2.JPG



Next, we plot all the venues on map using Folium library.
Then we group the data into clusters and represent the clusters on the map.


## RESULTS

###### Connaught Place on the map :-
https://github.com/DivS13/Coursera_Capstone/blob/master/Images/Map1.JPG

###### Restaurants in Connaught Place :-
https://github.com/DivS13/Coursera_Capstone/blob/master/Images/Map2.JPG

###### Bars in Connaught Place :-
https://github.com/DivS13/Coursera_Capstone/blob/master/Images/Map3.JPG

###### Hotels in Connaught Place :-
https://github.com/DivS13/Coursera_Capstone/blob/master/Images/Map4.JPG

###### All the venues around Connaught Place :-
https://github.com/DivS13/Coursera_Capstone/blob/master/Images/Map5.JPG

###### Clusters of venues :-
https://github.com/DivS13/Coursera_Capstone/blob/master/Images/Map6.JPG

###### Number of venues in each cluster :-
https://github.com/DivS13/Coursera_Capstone/blob/master/Images/Cluster.JPG

## DISCUSSION
As we can see on the map. Several venues have been grouped into 3 clusters. The circle representing the cluster has not been scaled according to the number of venues in a cluster. Rather they have been made the same size to display the sparsity/density, such that all 3 clusters are visible on the map and the venues can still be differentiated. We are more interested in the centre of the cluster as that will be our criteria for ideal location of hotel.

## CONCLUSION
The three clusters have different number of venues. Cluster number 1 has 84 venues. Cluster number 2 has 49 venues. Cluster number 3 has 17 venues.

Since 3rd cluster has only 17 venues and is also much sparse, it would not make much sense to book a hotel room in that area. Number of hotels in that area is also low. There won't be much choice for hotel either.

Cluster 2 and 3, both have lot of venues available. Cluster 2 has a lot of venues right along the center. Cluster 3 has a little less than twice the number of venues than Cluster 3.

Best place to stay would be near the center of Cluster 1 or CLuster 2.

