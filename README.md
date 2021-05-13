# FLARE-Fire-Activity

## Overview
This repository contains scripts for processing spatial data to develop a fire perimeter database for 8 ecozones across Northeastern Siberia and characterize fire activity

The paper can be found here

## Process

1. Process ecozone shapefile boundaries to upload as assets to GEE (Google Earth Engine)

2. Process Hotspot (i.e., thermal detection data) from MODIS (Moderate Resolution Imaging Spectroradiometer; November 2000-present), VIIRS (Visible Infrared Imaging Radiometer Suite; January 2012-present), and VIIRS NOAA-20 375 m data is available from January 2020-present. Data was acquire for Russia from [FIRMS](https://firms.modaps.eosdis.nasa.gov/download/create.php)


## Scripts

Develop fire perimeters from Landsat data

1. R Single-Ecozone-Boundary.Rmd --- create single boundary for 9 ecozones
2. R Hotspot-March-October.Rmd --- Select hotspots from March to October
3. R Hotspot-to-Polygon-Ecozone.Rmd --- Selects points with in  ROI Ecozones and converts  to Polygon
4. GEE FLARE-Binary-Harm-EA ---  create binary Burned image the is Harmonized  across landsat archive and process in Alber's Equal area
5. GEE FLARE-Vectorize-Harm-EA --- vectorize burned  ares in Binary image
6. R GEE-Vector-Ecozone-Shapefile-clean.Rmd --- combine vectors  from 3 ROI then buffer, remove holes, combine over lapping polygons, smooth and simlify vectors
7. R 2-GEE-Vector...---apply negative buffer to counter act previous buffer
8. R GEE-Vector-Ecozone-Attribute-Create.Rmd --- add attribiutes from hotspots, ecozones, calculate area burned, create unique ID


For Modis Burned area product
1. GEE
2. Modis-Burned-Area-Product-Summary

Analysis
