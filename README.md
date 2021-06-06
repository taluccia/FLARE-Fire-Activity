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

# Fire terminology

[Fire Effects Information System Glossary](https://www.fs.fed.us/database/feis/glossary2.html#1)

# References
**Hotspot point Shapefile**

**Ecozone Shapefile**
Olson, D. M., Dinerstein, E., Wikramanayake, E. D., Burgess, N. D., Powell, G. V. N., Underwood, E. C., D'Amico, J. A., Itoua, I., Strand, H. E., Morrison, J. C., Loucks, C. J., Allnutt, T. F., Ricketts, T. H., Kura, Y., Lamoreux, J. F., Wettengel, W. W., Hedao, P., Kassem, K. R. 2001. Terrestrial ecoregions of the world: a new map of life on Earth. Bioscience 51(11):933-938.
[Download location ](https://www.worldwildlife.org/publications/terrestrial-ecoregions-of-the-world)

**Yedoma Shapefile**
Strauss, Jens; Laboor, Sebastian; Fedorov, Alexander N; Fortier, Daniel; Froese, Duane G; Fuchs, Matthias; Grosse, Guido; Günther, Frank; Harden, Jennifer W; Hugelius, Gustaf; Kanevskiy, Mikhail Z; Kholodov, Alexander L; Kunitsky, Victor V; Kraev, Gleb; Lapointe-Elmrabti, Lyna; Lozhkin, Anatoly V; Rivkina, Elizaveta; Robinson, Joel; Schirrmeister, Lutz; Shmelev, Denis; Shur, Yuri; Siegert, Christine; Spektor, Valentin; Ulrich, Mathias; Vartanyan, Sergey L; Veremeeva, Alexandra; Walter Anthony, Katey M; Zimov, Sergey A (2016): Database of Ice-Rich Yedoma Permafrost (IRYP), link to ESRI shapefiles. PANGAEA, https://doi.org/10.1594/PANGAEA.861732,

[Download location](https://doi.pangaea.de/10.1594/PANGAEA.861732)

**Permafrost Shapefile**
Brown, J., O. Ferrians, J. A. Heginbottom, and E. Melnikov. 2001. Circum-Arctic Map of Permafrost and Ground-Ice Conditions, Version 2. [Indicate subset used]. Boulder, Colorado USA. NSIDC: National Snow and Ice Data Center. doi: https://doi.org/10.7265/skbg-kf16. [Date Accessed].

[permafrost shapefile details](https://nsidc.org/data/GGD318/versions/2/print)
