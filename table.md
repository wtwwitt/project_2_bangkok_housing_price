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
|nearby_bus_stops|int|the number of nearby bus stops|
|nearby_supermarkets|int|the number of nearby supermarkets|
|nearby_shops|int|the number of nearby shops|
|year_built|int|year built|
|facilities|list|list of facilities|


|Column|Description|Transformation|
|---|---|---|
|floor_area|total area of inside floor [㎡]|log + polynomial degree 2 + scaled|
|floor_level|floor level of the room|log + polynomial degree 2 + scaled|
|land_area|total area of the land [㎡]|log + polynomial degree 2 + scaled|
|total_units|the number of rooms/houses that the condo/village has|Polynomial degree 2 + scaled|
|bedrooms|the number of bedrooms|Polynomial degree 2 + scaled|
|baths|the number of baths|Polynomial degree 2 + scaled|
|nearby_stations|the number of nearby stations (within 1km)|polynomial degree 2 + scaled|
|nearby_supermarkets|the number of nearby supermarkets|polynomial degree 2 + scaled|
|nearby_shops|the number of nearby shops|polynomial degree 2 + scaled|
|year_built|year built|polynomial degree 2 + scaled|
|facilities|list of facilities|Converted to facilities count - polynomial degree 2 + scaled|
|nearby_bus_stops|the number of nearby bus stops|scaled|
|nearby_station_distance|list of (station name, distance[m]). <br/>Each station name consists of station ID, station name, and Line such as "E4 Asok BTS"|Dummified-like (to scaled distance)|
|dist_subdist|district + subdistrict name concatenated with some value corrections|Dummified|
|property_type|type of the house: Condo, Townhouse or Detached House|Dummified|


For XGBoost
|Column|Transformation|
|---|---|
|bedrooms|polynomial degree 2 + scaled|
|baths|polynomial degree 2 + scaled|
|nearby_stations|polynomial degree 2 + scaled|
|nearby_supermarkets|polynomial degree 2 + scaled|
|nearby_shops|polynomial degree 2 + scaled|
|nearby_station_distance|converted to distance mean + polynomial degree 2 + scaled|
|facilities|converted to facilities count - polynomial degree 2 + scaled|
|floor_area|scaled|
|floor_level|scaled|
|land_area|scaled|
|latitude|scaled|
|longitude|scaled|
|nearby_bus_stops|scaled|
|year_built|scaled|
|property_type|dummified|

|District|Subdistrict|
|---|---|
|Bangkok Yai|Wat Arun|
|Ratchathewi|Thung Phaya Thai|
|Bang Rak|Maha Phruettharam|
|Bang Rak|Suriyawong|
|Watthana|Khlong Tan Nuea|
|Pathum Wan|Rong Mueang|
|Khlong Toei|Khlong Tan|
|Watthana|Khlong Toei Nuea|
|Khlong Toei|Khlong Toei|
|Pathum Wan|Lumphini|