# Common API Reference

**Namespace:** `BingMapsSDSToolkit`

The following classes and enumerators are used through out the Bing Maps Spatial Data Services toolkit. 

* [BasicDataSourceInfo Class](#basicdatasourceinfo-class)
* [DistanceUnitType Enumerator](#distanceunittype-enumerator)
* [FileExtensionUtilities Class](#fileextensionutilities-class)
* [GeodataLocation Class](#geodatalocation-class)
* [Geography Class](#geography-class)
* [SpatialTools Class](#spatialtools-class)

## BasicDataSourceInfo Class

Basic information about a data source

### Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| AccessId | String | The access ID for the data source. |
| DataSourceName | String | Name fo the Data Source. |
| Description | String | A description of the data source data. |
| EntityTypeName | String | Name of the Entity type of the data source. |
| MasterKey | String | The master Bing Maps key for editting a data source. |
| QueryKey | String | The query Bing Maps key for querying a data source. |
| QueryUrl | String | The query URL for accessing the data source. |

## BingDataSources Class

A static class that contains data source information for all the built-in Bing data sources in the Bing Spatial Data Services.

### Static Properties

| Name | Type        | Description |
| ---- | ----------- | ----------- |
| FourthCoffeeSample | BasicDataSourceInfo | A sample data source of coffee shops. |
| NavteqPOIs_EU | BasicDataSourceInfo | A data source of points of interest for Europe.  |
| NavteqPOIs_NA | BasicDataSourceInfo | A data source of points of interest for North America.  |
| TrafficIncidents | BasicDataSourceInfo | A data source of real time traffic incidents (accidents, road closures, ...). |
| USCensus2010_111CD | BasicDataSourceInfo | A data source that contains a subset of 2010 US Census data broken up by 111th Congressional Districts. |
| USCensus2010_Counties | BasicDataSourceInfo | A data source that contains a subset of 2010 US Census data broken up by counties. |
| USCensus2010_States | BasicDataSourceInfo | A data source that contains a subset of 2010 US Census data broken up by states. |
| USCensus2010_ZCTA5 | BasicDataSourceInfo | A data source that contains a subset of 2010 US Census data broken up by Zip Code Tabulation areas (ZCTA5). |

## DistanceUnitType Enumerator

Units of measurements for distances.

| Name | Description |
| ---- | ----------- |
| Feet | Distances in Feet |
| KM | Distances in Kilometers. |
| Meters | Distances in Meters. |
| Miles | Distances in Miles |
| Yards | Distances in Yards |

## FileExtensionUtilities Class

Useful utilities for working with file extensions.

### Static Methods

| Name | Return Type | Description |
| ---- | ----------- | ----------- |
| GetFileExtensions(DataSourceFormat format, out String defaultExt, out String filters) | void | Give a data source format, this method provides a default and file extension filter string. |
| GetFileExtensions(BatchFileFormat format, out String defaultExt, out String filters) | void | Give a batch geocoding file format, this method provides a default and file extension filter string. |

## GeodataLocation Class

An object that stores the coordinate information.

### Constructor

> `GeodataLocation()` 

> `GeodataLocation(Double latitude, Double longitude)` 

### Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Latitude | Double | Latitude coordinate. |
| Longitude | Double | Longitude coordinate. |

## Geography Class

An object used to represent a geography column type.

### Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| WellKnownText | String | The well known text that describes the geography object. |

### Methods

| Name | Return Type | Description |
| ---- | ----------- | ----------- |
| NumPoints() | Int32 | Calculates the number of coordinate pairs in the geography. |

## SpatialTools Class

A set of useful spatial calculation tools.

### EarthRadius Property

The approximate spherical radius of the Earth

#### Constants

| Name | Description |
| ---- | ----------- |
| Feet | Earth Radius in Feet |
| KM | Earth Radius in Kilometers |
| Meters | Earth Radius in Meters |
| Miles | Earth Radius in Miles |

### Static Methods

| Name | Return Type | Description |
| ---- | ----------- | ----------- |
| ConvertDistance(Double distance, DistanceUnitType fromUnits, DistanceUnitType toUnits)| Double | Converts distances from one unit to another. | 
| GetEarthRadius(DistanceUnitType units) | Double | Retrieves the radius of the earth in a specific distance unit for WGS84. Defaults unit is in Meters. |
| HaversineDistance(GeodataLocation origin, GeodataLocation destination, DistanceUnitType units) | Double | Calculate the distance between two coordinates on the surface of a sphere (Earth). |
| HaversineDistance(Double origLat, Double origLon, Double destLat, Double destLon, DistanceUnitType units) | Double | Calculate the distance between two coordinates on the surface of a sphere (Earth). |
| ToDegrees(Double angle) | Double | Converts an angle that is in radians to degress. Angle * (180 / PI) |
| ToRadians(Double angle) | Double | Converts an angle that is in degrees to radians. Angle * (PI / 180) |
