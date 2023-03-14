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


<h1>Goals</h1>
<b>Goals:</b> To identify POIs in the text; To georeference the identified POIs; To use shortest paths, and travelling salesman methods to replicate the path.

<p><b>Background:</b> Following discussions about the work undertaken in <a href=”https://zenodo.org/record/4669886#.ZBB6GXbP0UE”>this paper</a>, the use of POIs as waypoints in written text was considered. The hypothesis 'Can 

  
<head>
<link rel="import" href="\\uol.le.ac.uk\root\staff\home\c\ch510\Downloads\Extracting Footpaths from Website and Replicating  (4) (1)[83]">
</head>
  
  
  
  
  
<h1>Data</h1>
<b>Source:</b> Edina Digimap
<p><b>Product:</b> 1st Edition (1846-1899) County Series 1:10 <br /><b>Format:</b> Tiff

<p><h1>Method</h1>
The method used is developed from that in this YouTube video: www.youtube.com/watch?v=QMTUFfE2VXo&ab_channel=AnujTiwari. <p>

1. Download the data from Edina Digimap and import it into ArcMap as a TIFF file <br />
2. Create a new polygon bounding box, and clip the input TIFF to the study site area. <br /> 
3. Enable the ArcScan Extension and Toolbar <br />
4. In the TIFF file symbology settings, represent the data using unique values (0 & 1) <br />
5. Using the 'Raster Cleanup' tool in the ArcScan toolbar, with the TIFF file selected, start editing and selecting cells you want to remove. In this example, we are removing any raster cells which are not buildings.  <br />
6. Once all non-building related raster cells are deleted, and the 'Raster Cleanup' session is completed, use the 'raster to polygon' tool (found by searching the toolbox).  <br />
7. Delete the polygon representing the background, to extract the building polygons. <br />
8. Use the 'Dissolve' tool to clean up the individual polygons into one large polygon to represent all buildings (if desired).  <br />
 <br />

![Editing a markdown file for a talk](/images/test_mkth_builds_raster_tidy.PNG)

<img src="https://github.com/CharlieHewitt1/charliehewitt1.github.io/blob/master/images/test_mkth_builds_raster_tidy.PNG" alt="Italian">






<h1>Results</h1>
