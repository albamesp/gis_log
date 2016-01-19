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

#### Processing Toolbox
View > Panels > Processing Toolbox

#### Plugins
Plugins > Open and Install Plugins > ... 

    - OpenLayers Plugin (access through Web > OpenLayers Plugin)
        Allows access to open mapping layers -- Bing; GoogleMaps etc, requires Internet Connections

    - GPS Tools
        Can create points, lines and polygons from GPS data -- and can also do vice versa. Therefore, can create paths into the GPS and follow it.

#### Digitising

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

##### Layer Properties
Right-click on layer > Properties

Can adjust symbology, and other options.
    Styles can be saved as .qml files -- where the styles can be used on many shapefiles (as they are rule-based).
        e.g. if you save a .qml style file where it uses the column 'type' to decide land cover type; where 1 is green, 2, blue, etc., if you use this style file on any shape file that has a type column/field and the correct attribute is will work.



# Ideas/ notes for PhD/ Life

## Change detection
Useful/ interesting tip. use one band (say band 5, red from Landsat) from three different years say, and then view them as RGB. R: Band 5 oldest; B: Band 5 older; G: Band 5 current. Obviously only shows you change in band 5 (or whatever band you use). There are more indepth change detection algorithms available.

## GPS points -- cycle, walking tracks, photomaps.
GPS Tools plugin!


