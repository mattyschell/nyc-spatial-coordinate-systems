# nyc-spatial-coordinate-systems

## Quick Reference

| EPSG Code  | Description | ESRI Software | Lower Left X | Lower Left Y | Upper Right X | Upper Right Y | 
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| [2263](https://spatialreference.org/ref/epsg/2263/)  | New York State Plane Lambert Conformal Conic  | NAD 1983 StatePlane New York Long Isl FIPS 3104 (US Feet) | 900000 | 110000 | 1090000 | 295000 |
| [3857](https://spatialreference.org/ref/epsg/3857/) | Web Mercator | WGS 1984 Web Mercator (auxiliary sphere) | -8271348.9 | 4934214.8 | -8195010.6 | 5008764.4 |
| [4326](https://spatialreference.org/ref/epsg/4326/) | WGS84 World Geodetic Coordinate System | WGS 1984 | -74.3027914 | 40.4681991 | -73.61703247 | 40.97574288 |
| [6539](https://spatialreference.org/ref/epsg/6539/)  | (NAD 2011) New York State Plane Lambert Conformal Conic | NAD 1983 (2011) StatePlane New York Long Isl FIPS 3104 (US Feet) | 900000 | 110000 | 1090000 | 295000 |


## Glossary 

From earthy to mappy

### Geoid
* A lumpy earth model that is equal gravity global mean sea level. 
* It is lumpy because of gravitational variations.
* Different stuff under our feet (mountains, dinosaur bones) changes gravity and its direction.  

### Global Ellipsoid
* A decent approximation of the geoid.
* It is geocentric - a mathematical model with the earth at the center
* Wider at the equator than vertically to the poles
* WGS 84, the most common latitude/longitude geographic coordinate system, uses a global ellipsoid.
* Technically the global ellipsoid is a spheroid. When 2 of 3 ellipsoid axes are equal this is a spheroid.  A spheroid is a type of ellipsoid like a square is a type of rectangle.
  
### Local Ellipsoid
* Also known as a reference ellipsoid.
* An ellipsoid fitted nicely to one section of the earth.
* Can be fixed to tectonic plates and adjusted with the movement of ground control points.

### Datum
* Based off of an ellipsoid with elevation. 
* Local datums are based on local ellipsoids. NAD 83 is a local datum based on a local ellipsoid.
* Global datums are based on global ellipsoids. WGS 84 is a global datum based on a global ellipsoid.
* When expressed as latitude/longitude these are GEOGRAPHIC COORDINATE SYSTEMS

### Projection
* Flattening of datums onto flat surfaces like screens and maps
* Lambert Conformal Conic is a common projection used by cities and states
* When expressed as x/y coordinates these are PROJECTED COORDINATE SYSTEMS

## North American Datums and Corresponding NYC Projected Coordinate Systems 

The positional shifts in these coordinate reference systems can be up to about 3 feet. It is always best to state precisely which one a dataset uses.

| Name  | Spatial Reference ID | Notes | 
| ------------- | ------------- | ------------- | 
| NAD 83 / New York Long Island | https://spatialreference.org/ref/epsg/2263/ | NAD 83 was released in 1986 so sometimes referred to as NAD 83 (86) |
| NAD83 (HARN) / New York Long Island | https://spatialreference.org/ref/epsg/2908/ | HARN = High Accuracy Reference Network |
| NAD 83 (CORS) New York Long Island | https://spatialreference.org/ref/esri/103499/ | CORS = Continuously Operating Reference Stations |
| NAD83 (NSRS2007) / New York Long Island | https://spatialreference.org/ref/epsg/3628/ |  http://www.ngs.noaa.gov/NationalReadjustment/ |
| NAD83 (2011) / New York Long Island | https://spatialreference.org/ref/epsg/6539/ | http://www.ngs.noaa.gov/web/surveys/NA2011/ |
| New York Long Island State Plane Coordinate System of 2022 | 361004 | To be released in 2027. A [Hotine Oblique](https://en.wikipedia.org/wiki/Oblique_Mercator_projection#Hotine_oblique_Mercator_projection) projection based on the North American Terrestrial Reference Frame of 2022 |


## NYC GIS Data Transformation Details 

| Dataset | Source Coordinate System | Published | Published Coordinate System | Transformation Used |
| ------------- | ------------- | ------------- | ------------- | ------------- | 
| [building footprints](https://github.com/mattyschell/geodatabase-buildings) | [2263](https://spatialreference.org/ref/epsg/2263/) | [ArcGIS Online](https://nyc.maps.arcgis.com/home/item.html?id=870bf69e8a8044aea4488e564c0b4010) | [3857](https://spatialreference.org/ref/epsg/3857/) | NAD 83 <-> WGS 1984 (ITRF00) to NAD 83 <-> WGS 1984 |
| CSCL | [2263](https://spatialreference.org/ref/epsg/2263/) | [ArcGIS Online](https://nyc.maps.arcgis.com/home/index.html) | [3857](https://spatialreference.org/ref/epsg/3857/) | NAD 83 <-> WGS 1984 (ITRF00) to NAD 83 <-> WGS 1984 |
| [Planimetrics 2012/2014](https://github.com/CityOfNewYork/nyc-planimetrics/tree/planimetrics-2014) | [2263](https://spatialreference.org/ref/epsg/2263/) | [ArcGIS Online](https://nyc.maps.arcgis.com/home/index.html) | [3857](https://spatialreference.org/ref/epsg/3857/) | NAD 83 <-> WGS 1984 (ITRF00) to NAD 83 <-> WGS 1984 |
| [Planimetrics 2012/2014](https://github.com/CityOfNewYork/nyc-planimetrics/tree/planimetrics-2014) | [2263](https://spatialreference.org/ref/epsg/2263/) | [NYC Open Data](https://opendata.cityofnewyork.us/) | [2263](https://spatialreference.org/ref/epsg/2263/)  | None |
| [Planimetrics 2022](https://github.com/CityOfNewYork/nyc-planimetrics/blob/main/Capture_Rules.md) | [2263](https://spatialreference.org/ref/epsg/2263/) | [ArcGIS Online](https://nyc.maps.arcgis.com/home/index.html) | [3857](https://spatialreference.org/ref/epsg/3857/) | NAD 83 <-> WGS 1984 (ITRF00) to NAD 83 <-> WGS 1984 |
| [NYC Map Tiles](https://api-portal.nyc.gov/api-details#api=geoserver-tile-services-api&operation=tmsGetTileMetadata) | [2263](https://spatialreference.org/ref/epsg/2263/) | maps.nyc.gov | [900913](https://spatialreference.org/ref/epsg/900913/) | 2263 <-> WGS84.  No datum transformation |


## Background Reading

* [history of NYC coordinate reference systems](https://nycitymap.wordpress.com/2016/09/13/nyc-projected/)
* [presentation on projections and coordinate systems](http://mjfoster83.github.io/projections/index.html#/)
* [datum tutorial](https://vdatum.noaa.gov/docs/datums.html)
* [historical surveys and systems in NYC](https://web.archive.org/web/20191011125423/https://www.pobonline.com/articles/89732-web-exclusive-the-xs-and-ys-of-the-big-apple)
* [1914 NYC leveling and benchmarks](https://web.archive.org/web/20191011125423/https://www.pobonline.com/articles/89732-web-exclusive-the-xs-and-ys-of-the-big-apple)
* [NY Times article on height modernization](https://web.archive.org/web/20191011125423/https://www.pobonline.com/articles/89732-web-exclusive-the-xs-and-ys-of-the-big-apple)
* [NY Times article on the end of the US Survey foot](https://web.archive.org/web/20200819115447/https://www.nytimes.com/2020/08/18/science/foot-surveying-metrology-dennis.html)
* Differences between NAD 83 and WGS 84
   * [ESRI Summary](https://support.esri.com/en-us/knowledge-base/how-to-determine-which-nad1983towgs1984-transformation-000005929)
   * [Canadian presentation](http://naref.org/transf/nad83_hydroscan2006.pdf)
* Preparing for the NSRS of 2022
	* [National Geodetic Survey](https://www.ngs.noaa.gov/datums/newdatums/GetPrepared.shtml)
	* [ESRI](https://www.esri.com/arcgis-blog/products/arcgis-pro/data-management/prepare-your-data-for-the-nsrs-2022)
	* [Zone map](https://experience.arcgis.com/experience/dddb7bc0be6f4e56a1c370c8d529d1a0)


## FAQ

### In PostGIS how do I perform a datum-shifted transformation from WGS84 to New York state plane? 

A: Many people are asking.  

ESRI's ArcGIS Pro and ArcGIS Online perform the shift by default.  Data produced in PostGIS may appear "shifted" by approximately 3 feet using the default ST_Transform.

Here's the world-famous Flatiron Building and 2 of its address points.  Red is the source data displayed in New York State Plane Lambert Conformal Conic. Yellow is WGS84 lon/lat data transformed without a datum shift.

![World Famous Flatiron Building](images/flatiron.png)

Here's the world-famous ArcGIS Pro transformation details. 

![World Famous ArcGIS Pro](images/esri-transformation-details.png)

PostGIS uses the "proj" open source database.  It's stored as SQLLite in a location like this on Windows - C:\Program Files\PostgreSQL\16\share\contrib\postgis-3.5\proj\proj.db

That database includes a table named "helmert_transformation_table."  This table is named after our man [Friedrich Helmert](https://en.wikipedia.org/wiki/Helmert_transformation). The ESRI code 108190 is in there.

```sql
select
	auth_name,
	code,
	name,
	source_crs_auth_name,
	source_crs_code,
	target_crs_auth_name,
	target_crs_code
from
	helmert_transformation_table
where
	code = 108190
```

| auth_name | code   | name                         | source_crs_auth_name | source_crs_code | target_crs_auth_name | target_crs_code |
|-----------|--------|------------------------------|-----------------------|------------------|-----------------------|------------------|
| ESRI      | 108190 | WGS_1984_(ITRF00)_To_NAD_1983 | EPSG                  | 4326             | EPSG                  | 4269             |

To use this in PostGIS you will need a fairly recent version (3.4+)  that includes [ST_TransformPipeline](https://postgis.net/docs/manual-3.4/ST_TransformPipeline.html).

Here is a transformation without the datum shift.

```sql
select
	ST_Transform(ST_SETSRID(ST_MakePoint(-73.98272, 40.74518)
                           ,4326)
                ,2263);
```

--> POINT (989038.1655756367 210766.27823605755)

Here it is with the shift. This is the answer to the FAQ.

```sql
select
	ST_Transform(ST_TransformPipeline(  
    				ST_SetSRID(ST_MakePoint(-73.98272, 40.74518), 4326)
       			   ,'urn:ogc:def:coordinateOperation:ESRI::108190'
       			   ,4269)
       		   ,2263);
```

--> POINT (989038.5660188518 210763.2676373856)

These points are approximately 3 feet apart.

Here's the inverse, going from New York State Plane to WGS84. It's a mirror image of the forward direction!

```sql
select 
	ST_InverseTransformPipeline(ST_Transform(
									ST_SetSRID(ST_MakePoint(989038.5660188518,210763.2676373856),2263)
								   ,4326)
								,'urn:ogc:def:coordinateOperation:ESRI::108190'
								,4269);
```

### How many decimal digits of precision should I use for data in latitude longitude?

A: Use 7 if you are a normal person doing normal GIS work.

The sixth decimal digit represents the limit of most forms of data collection such as heads up digitizing  or GPS. The sixth digit (0.000001 degrees) is approximately 4 inches at the equator. By including one more digit, the seventh, you ensure that any rounding or other calculations take place in the 7th digit. This keeps the possibly meaningful 6th digit stable.

Internally most geographic information systems store and operate on data using [floating point numbers](https://en.wikipedia.org/wiki/Floating-point_arithmetic). So while it may be helpful to think about limiting your digits on input, display, and across networks, if you are a GIS person doing GIS work on a computer you are not helping yourself by thinking about significant digits.

### If I have important, accurate data in New York State Plane (underlying NAD 83) is it ever OK to present, store, or transform via WGS84 or Web Mercator?

A: No

### How much difference is there between all of these NYC coordinate systems?

Here's the tip of the ["prow"](https://en.wikipedia.org/wiki/Flatiron_Building#Base) of the world famous Flatiron Building. The source data is stored in spatial reference [2263](https://spatialreference.org/ref/epsg/2263/) which uses the original North American Datum of 1983.  

The point at the tip of the prow is labeled "NAD 83."

![prow zoomed out](images/prow-zoomed-out.png)

We can project this point to different realizations of NAD 83. We can also project to the World Geodetic System of 1984, commonly used in GPS and web maps.  These points are labeled with selected distances displayed.

Zoomed in a little from the previous image:

![prow zoomed in 1](images/prow-zoomed-in-1.png)

Zoomed in more to show all of the NAD 83 realizations.

![prow zoomed in 2](images/prow-zoomed-in-2.png)

If you use ArcGIS Pro the trick to visualize these distances is to disable automatic transformations between coordinate systems.

![do not transform](images/do-not-transform.png)

### What is the correct way to bring NAD 83 data up to the present realization?

"The correct way to convert data in historic U.S. datums is to transform them through all in-between NAD83 datums." ([source](https://www.esri.com/arcgis-blog/products/arcgis-pro/data-management/prepare-your-data-for-the-nsrs-2022)) For New York State Plane:

1. https://spatialreference.org/ref/epsg/2263/
2. https://spatialreference.org/ref/epsg/2908/
3. https://spatialreference.org/ref/epsg/3628/ 
4. https://spatialreference.org/ref/epsg/6539/


### Can ArcGIS Pro Transform NAD83 data on the fly?

Not exactly.  The ArcGIS Pro transformation dropdown returns paths with a maximum of two hops.  Here for example are the available transformations for data in 2263 (NAD 83) transformed on the fly to a map in 6539 (NAD 83 2011)

![arcgis pro on the fly](images/arcgispro-on-the-fly.png)

Anything that goes through WGS 84 is a bad idea. See the pictures in the FAQ above. Ideally the data itself would be reprojected (see the previous FAQ). The ArcGIS Pro project tool allows you to chain a series geographic transformations in a single run of the tool. 

But if forced to choose on the fly perhaps "NAD 83 to NAD 1983 HARN 47 + NAD 1983 HARN to NAD 1983 2011"? That's the answer to the FAQ?





