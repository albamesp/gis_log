# QGIS course notes

## Day 1

### Geographic Projections & Datums

Whilst QGIS deals with Datums, and with on-the-fly (OTF) projections, you must be careful!

### Project and geodatabase approaches

Projects, are standalone, where as geodatabases provide more 'central' repositories for data for ease of accessibility.

Projects are the scope of this course.

### Data types

#### Vector Data
- points;
- polylines -- series of nodes/ points connected;
- polygons.

These are stored in shapefiles (.shp), which not only record geographic information, but can also record attribute data (within the database, or 'attribute table')

#### Raster Data
Representation of environments within grids, using pixels -- of varying spatial resolutions -- where each pixel has a value (these data do not have attribute tables, and therefore only have one number/ attribute associated to them).

Usually this pixel value is a reflectance number -- in the case of satellite observation data.



### QGIS Set-up

#### Setting up a CRS
QGIS > Preferences > CRS tab > automatic enable OTF
                             > CRS for new layers

The CRS displayed at the bottom RH corner of the QGIS window is the CRS of the Canvas -- NOT of the layer!

Change all three to the projection you'd like to use.

*Remember to change back the CRS QGIS options for my PhD stuff*

27700 -- British National Grid, for OS data

4326 -- WGS84, Psuedo Mercator

#### Processing Toolbox
View > Panels > Processing Toolbox

#### Zoom Factor
QGIS > Preferences > MapTools > Zoom Factor = ~1.1 ish for better zooming on Macs

#### Plugins
Plugins > Open and Install Plugins > ... 

    - OpenLayers Plugin (access through Web > OpenLayers Plugin)
        Allows access to open mapping layers -- Bing; GoogleMaps etc, requires Internet Connections

    - GPS Tools
        Can create points, lines and polygons from GPS data -- and can also do vice versa. Therefore, can create paths into the GPS and follow it.
        
    - Terrain Analysis
        Can create various analyses of terrain data -- slope, ruggedness, etc.

### Digitising Vector Data

##### Creating a new Shapefile
New shapefile layer button (with asterisk) > type (points) > save to working directory ('projects/')

##### Digitising
QGIS > Preferences > Digitising tab > Surpress attribute form pop-up

Toggle editing using yellow pencil. Can create points/ polygons/ polylines. 

Right-click on layer, and 'Open Attribute Table' to edit attributes of points.

##### Advanced Digitising Toolbar
Includes tools for reshaping, donuting, splitting.

##### Snapping -- when you want adjacent polygons, or polylines that share common nodes
Settings > Snapping Options > On/ Off/ etc. (with thresholds too.)
    Enable topological editing too. This means that when creating/ digitising shapes, they will line up, if sharing common edge.

#### Layer Properties
Right-click on layer > Properties

Can adjust symbology, and other options.
    Styles can be saved as .qml files -- where the styles can be used on many shapefiles (as they are rule-based).
        e.g. if you save a .qml style file where it uses the column 'type' to decide land cover type; where 1 is green, 2, blue, etc., if you use this style file on any shape file that has a type column/field and the correct attribute is will work.


### Working with Raster Data
Set CRS to Psuedo Mercator (4326)

#### Symbology
Changing symbology for Raster data is slightly diff than for Vector files -- pseudocolour for renditions that aren't B&W

#### To merge adjacent raster files
Raster > Miscellaneous > Merge...

No data value -- only tick this box if we have areas of no data, and it changes these values to the number specified.

#### Clipping a raster 
Raster > Extraction > Clipper...

When clipping you can use an 'extent' -- this can be a drawn square, whilst tool box is open (and this fills in 'extent'); 
or a 'mask layer,' such as a shape file you enter.

#### Contouring
Raster > Exctraction > Contour...

#### Terrain Analysis
*Slope* -- z factor, a correction factor for calculating slope. this is coordinate system specific (apparently?) Here it is 10000, the actual number "doesn't really matter."

*Aspect* -- calculates direction of slope, degrees from 0. Caution: value 10, 10 degrees from 0, and 350 degrees from 0. Despite these two angles (both 10 degrees from north) only being 20 degrees apart, numerically they are much farther apart... *think* before analysis.

*Hillshade* -- presents a hillshade map, illuminated by a specified sun angle. (azimuth, and altitude)

*Ruggedness Index* -- produces a relative index by looking at surrounding pixels for relative elevation.

### Print Composer 
For outputting maps to file.

Add new map > then drag data frame.

To move things within the data frame go to: Layout > Move Content *Really useful, why didn't I know this before!?*


# Ideas/ notes for PhD/ Life

## Change detection
Useful/ interesting tip. use one band (say band 5, red from Landsat) from three different years say, and then view them as RGB. R: Band 5 oldest; B: Band 5 older; G: Band 5 current. Obviously only shows you change in band 5 (or whatever band you use). There are more indepth change detection algorithms available.

## GPS points -- cycle, walking tracks, photomaps.
GPS Tools plugin! For Garmin? and phone apps?

## Ruggedness Index on MODIS Mosaic of Greenland (MoG)
Try this, not sure whether the ruggedness algorithm does the right thing? As in, what is its search window?
May have to smooth the results...!


