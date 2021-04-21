# FLARE-Fire-Activity

## Overview
This repository contains scripts for processing spatial data to develop a fire perimeter database for 8 ecozones across Northeastern Siberia and characterize fire activity

The paper can be found here

## Process

1. Process ecozone shapefile boundaries to upload as assets to GEE (Google Earth Engine)

2. Process Hotspot (i.e., thermal detection data) from MODIS (Moderate Resolution Imaging Spectroradiometer; November 2000-present), VIIRS (Visible Infrared Imaging Radiometer Suite; January 2012-present), and VIIRS NOAA-20 375 m data is available from January 2020-present. Data was acquire for Russia from [FIRMS](https://firms.modaps.eosdis.nasa.gov/download/create.php)


## Scripts

Develop fire perimeters from Landsat data

1. Single-Ecozone-Boundary.Rmd --- create single boundary for 9 ecozones
2. Hotspot-March-October.Rmd --- Select hotspots from March to October
3. Hotspot-to-Polygon-Ecozone.Rmd --- Selects points with in  ROI Ecozones and converts  to Polygon
4. GEE Binary Burned image
5. GEE Vectorize
6. GEE-Vector-Ecozone-Shapefile-clean
7. GEE-Vector-Ecozone-Attribute-Create


For Modis Burned area product
1. GEE
2. Modis-Burned-Area-Product-Summary

Analysis
