# Executive Summary

Do you ever have a problem with housing price when trying move to a new home ?

Housing price in Bangkok is normally fluctuated due to many factors, some factors are considered to be positive for the price, but is that always true ?

This project analysis will explore the factors in Bangkok Housing Price data, so that we can aproximately tell about the price of houses in Bangkok and perimeters,<br/>
and that should gives some useful information for whoever you are, seller or buyer.

### Bangkok Housing Price Data
---
|Column|Type|Description|
|---|---|---|
|id|int|ID of selling item|
|province|string|province name: this dataset only includes Bangkok,Samut Prakan and Nonthaburi|
|district|string|district name|
|subdistrict|string|subdtistrict name|
|address|string|address e.g. street name, area name, soi number|
|property_type|string|type of the house: Condo, Townhouse or Detached House|
|total_units|float|the number of rooms/houses that the condo/village has|
|bedrooms|int|the number of bedrooms|
|baths|int|the number of baths|
|floor_area|float|total area of inside floor [㎡]|
|floor_level|int|floor level of the room|
|land_area|float|total area of the land [㎡]|
|latitude|float|latitude of the house|
|longitude|float|longitude of the house|
|nearby_stations|int|the number of nearby stations (within 1km)|
|nearby_station_distance|list|list of (station name, distance[m]). <br/>Each station name consists of station ID, station name, and Line such as "E4 Asok BTS"|
|nearby_bus_stops|int|the number of nearby bus stops|
|nearby_supermarkets|int|the number of nearby supermarkets|
|nearby_shops|int|the number of nearby shops|
|year_built|int|year built|
|month_built|string|month built: January-December|
|facilities|list|list of facilities|
|price|float|selling price|

This analysis will use the data to create housing price prediction model using Linear Regression with/without some regularization.

### By experimenting with many models, the best one will be using the follow factors for prediction
___
* District
* Subdistrict
* Property type
* Total units
* Number of bedrooms
* Number of bathrooms
* Total area of inside floor [㎡]
* Floor level
* Total area of the land [㎡]
* Number of nearby stations (within 1km)
* List of nearby stations with its distance
* Number of nearby supermarkets
* Number of nearby shops
* Year built
* Number of facilities

As there is a lot of missing data, various techniques is used to ensure that model training data is enough for better prediction accuracy,
along with some transformations on the original data.

### The results
___
Final model can explain 79.8% of data with the average error of 971K baht approximately.

The following factors are significantly affect housing price positively.
* Floor area
* Number of nearby stations (within 1km)
* Number of bathrooms
* Total area of the land
* Year built
* Number of bedrooms

locating neaby these stations will raise approximated price as well.
* BL11 Bang Sue MRT
* BL32 Itsaraphap MRT
* B9 Rama IX Bridge BRT

and the following are top 10 district/subdistrict that will have higher housing price according to the model.
|District|Subdistrict|
|---|---|
|Bang Rak|Maha Phruettharam|
|Bang Rak|Suriyawong|
|Watthana|Khlong Tan Nuea|
|Pathum Wan|Rong Mueang|
|Watthana|Khlong Toei Nuea|
|Bang Rak|Si Phraya|
|Bang Kho Laem|Bang Kho Laem|
|Pathum Wan|Lumphini|
|Khlong Toei|Khlong Tan|
|Bang Rak|Silom|

