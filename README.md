# nyc-spatial-coordinate-systems


## Quick Reference

| EPSG Code  | Description | ESRI Software Name | lower Left X | Lower Left Y | Upper Right X | Upper Right Y | 
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| [2263](https://epsg.io/2263)  | NAD 83 NY State Plane Projection Lambert Conformal (shape preserving) Conic  | NAD_1983_StatePlane _New_York_Long_Island_FIPS_3104_Feet | 900000 | 110000 | 1090000 | 295000 |
| [6539](https://epsg.io/6539)  | NAD 2011 NY State Plane Projection | NAD 1983 (2011) StatePlane New York Long Isl FIPS 3104 (US Feet) | 900000 | 110000 | 1090000 | 295000 |
| [4326](https://epsg.io/4326) | WGS84 Geographic Coordinate System, GRS 1980 Reference Ellipsoid Global Datum | GCS_WGS_1984 | -74.3027914 | 40.4681991 | -73.61703247 | 40.97574288 |
| [4269](https://epsg.io/4326) | NAD 83 GRS 1980 Reference Ellipsoid Local Datum | GCS_North_American_1983 | -74.3027914 | 40.4681991 | -73.61703247 | 40.97574288 |
| [3857](https://epsg.io/3857) | Web Mercator: Underlying WGS 84 coordinates projected to a sphere | WGS_1984_Web_Mercator_Auxiliary_Sphere | -8271348.9 | 4934214.8 | -8195010.6 | 5008764.4 |

## Glossary
From earthy to mappy

**geoid**
* a lumpy earth model that is equal gravity global mean sea level 
* it is lumpy because of gravitational variations
* different stuff under our feet (mountains, dinosaur bones) changes gravity 

**global ellipsoid**
* a decent approximation of the geoid
* wider at the equator than tall at the poles
* WGS 84, the most common lat/lon geographic coordinate system, uses a global ellipsoid
* technically when 2 of 3 ellipsoid axes are equal this is a spheroid.  A spheroid is a type of ellipsoid like a square is a type of rectangle

**local ellipsoid**
* also known as a reference ellipsoid
* an ellipsoid fitted nicely to one section of the earth
* we just use the part that is nicely fitted, the other parts are inside the earth or outer space

**datum**
* based off of ellipsoids with elevation. 
* can be local datums based off of local ellipsoids (ex NAD 83)
* can be global datums based off of global ellipsoids (ex WGS 84)
* when expressed as lat/lon these are GEOGRAPHIC COORDINATE SYSTEMS

**projections**
* flattening of datums onto flat surfaces like screens and maps
* lambert conformal conic is a common projection for local city and state agencies
* when expressed as x,y these are PROJECTED COORDINATE SYSTEMS

## North American Datums and Corresponding NYC Projected Coordinate Systems 

The positional shifts in these coordinate reference systems can be up to about 3/4 of a meter. It is always best to state precisely which one a dataset uses.

| Name  | EPSG Code | Notes | 
| ------------- | ------------- | ------------- | 
| NAD 83 | http://epsg.io/2263 |  |
| NAD 83 (HARN) | http://epsg.io/2908 | Harn = High Accuracy Reference Network |
| NAD 83 (CORS) | ? |  |
| NAD 83 2007 readjustment | http://epsg.io/3628 |  http://www.ngs.noaa.gov/NationalReadjustment/ |
| NAD 83 2011 readjustment | http://epsg.io/6539 | http://www.ngs.noaa.gov/web/surveys/NA2011/ |
| NAPGD2022 |  |  |


## Known Processes in NYC GIS and Their Coordinate Reference System Processing

## Helpful References

A blog post describing the NYC coordinate reference system history: https://nycitymap.wordpress.com/2016/09/13/nyc-projected/

