---
title: 'Replicating Written Descriptions of Footpaths in a GIS'
date: 2023-1-20
permalink: /posts/2012/08/blog-post-2/
tags:
  - QGIS
  - Python
  - Footpaths
  - Geoparse
---
Summary: Identifying points of interest (POIs) in written text descriptions of footpaths, and using those POIs to establish a map-version of the described routes. 


<h1>Aim</h1>
To extract walking route descriptions from a website, identify key points of interest from the text, and replicate the walked route using GIS methods.


<h1>Summary of Steps</h1>
* Extracting walking route data from www.visorando.co.uk
* Identifying the key POIs near walking routes
* Replicating the footpath using the key points of interest

<h1>Data</h1>
<b>Source:</b> Walking route descriptions from www.visorando.co.uk
* <p><b>Product:</b> A walk around Melbourn & Meldreth * <br /><b>Format:</b> Text
<b>Source:</b> UK Rights of Way 
* <p><b>Product:</b> Footpaths & byways - www.rowmaps.com * <br /><b>Format:</b> kml of linear features
<b>Source:</b> OSM Points of Interest (POIs) 
  * <p><b>Product:</b> POIs from the <a href="https://plugins.qgis.org/plugins/QuickOSM/">QuickOSM QGIS Plugin</a> * <br /><b>Format:</b> point features
<b>Source:</b> Ordnance Survey Road Network 
  * <p><b>Product:</b> <a href="https://digimap.edina.ac.uk/">OS Roads </a> * <br /><b>Format:</b> geodatabase of linear features  
  
<p><h1>Method</h1>
<b>Methods/Tools used:</b> QGIS, Python, Geoparsing, Network Analysis, Steiner Trees, Travelling Salesman.

<h2>Data Preparation</h2>
<b>UK Rights of Way Data:</b>
* Download data from the www.visorando.co.uk website
* Open QGIS and import the GML file keeping all layers
* Merge each layer ("footpaths", "bridleways", "byways") into a single 'walking network' dataset
* Clip to the study area using a pre-made study area polygon

<b>UK Road Network Data:</b>
* Download road network data from the https://digimap.edina.ac.uk/ website
* Open QGIS and import all layers
* Merge each road network type into a single 'road network' dataset
* Clip to the study area using a pre-made study area polygon

<b>Network dataset:</b>
* Merge the UK Road Network data & UK Rights of Way data once processed, into a single dataset to represent the network


<b>OSM Points of Interest (POI):</b>
* Using the QuickOSM Plugin in QGIS (https://plugins.qgis.org/plugins/QuickOSM/) import the point, line, and polygon data relating to the 'historic', 'leisure', 'man-made', 'sport', 'waterway', 'tourism', 'natural', and 'amenity' POI types.
* Create one 'points object', 'lines object', 'polygons object' for each data representation using the merge function.
* Clip these data to the study area using the pre-made polygon
* Export each of the three objects as a csv files



<img src="https://github.com/CharlieHewitt1/charliehewitt1.github.io/blob/master/images/test_mkth_builds_raster_tidy.PNG" alt="Italian">






<h1>Results</h1>
