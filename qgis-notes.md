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
QGIS > Preferences > CRS tab > automatic, enable OTF

The CRS displayed at the bottom RH corner of the QGIS window is the CRS of the Canvas -- NOT of the layer!

#### Remember to change back the CRS QGIS options for my PhD stuff

#### Processing Toolbox
View > Panels > Processing Toolbox



# Ideas/ notes for PhD
##### Change detection
- useful/ interesting tip. use one band (say band 5, red from Landsat) from three different years say, and then view them as RGB. R: Band 5 oldest; B: Band 5 older; G: Band 5 current. Obviously only shows you change in band 5 (or whatever band you use). There are more indepth change detection algorithms available.
    


