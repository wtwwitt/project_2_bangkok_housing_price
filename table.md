|Column|Type|Description|
|---|---|---|
|district|string|district name|
|subdistrict|string|subdtistrict name|
|property_type|string|type of the house: Condo, Townhouse or Detached House|
|total_units|float|the number of rooms/houses that the condo/village has|
|bedrooms|int|the number of bedrooms|
|baths|int|the number of baths|
|floor_area|float|total area of inside floor [㎡]|
|floor_level|int|floor level of the room|
|land_area|float|total area of the land [㎡]|
|nearby_stations|int|the number of nearby stations (within 1km)|
|nearby_station_distance|list|list of (station name, distance[m]). <br/>Each station name consists of station ID, station name, and Line such as "E4 Asok BTS"|
|nearby_supermarkets|int|the number of nearby supermarkets|
|nearby_shops|int|the number of nearby shops|
|year_built|int|year built|


|Column|Description|Transformation|
|---|---|---|
|floor_area|total area of inside floor [㎡]|log + polynomial degree 2|
|floor_level|floor level of the room|log + polynomial degree 2|
|land_area|total area of the land [㎡]|log + polynomial degree 2|
|total_units|the number of rooms/houses that the condo/village has|Polynomial degree 2|
|bedrooms|the number of bedrooms|Polynomial degree 2|
|baths|the number of baths|Polynomial degree 2|
|nearby_stations|the number of nearby stations (within 1km)|polynomial degree 2|
|nearby_supermarkets|the number of nearby supermarkets|polynomial degree 2|
|nearby_shops|the number of nearby shops|polynomial degree 2|
|year_built|year built|polynomial degree 2|
|nearby_station_distance|list of (station name, distance[m]). <br/>Each station name consists of station ID, station name, and Line such as "E4 Asok BTS"|Dummified (to normalized distance)|
|dist_subdist|district + subdistrict name concatenated|Dummified|
|property_type|type of the house: Condo, Townhouse or Detached House|Dummified|