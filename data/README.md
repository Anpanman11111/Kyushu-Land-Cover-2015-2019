# Data Description
This folder contains processed raster files used in the land cover change analysis. All data is clipped to the Kyushu region.

### Kyushu_2015.tif
- Original 2015 Copernicus Land Cover raster clipped to Kyushu boundary
- Unmodified land cover classes

### Kyushu_2019.tif
- Original 2019 Copernicus Land Cover raster clipped to Kyushu boundary 
- Unmodified land cover classes

### Kyushu_Reclassified_2015.tif
- Reclassified version of the 2015 raster
- Re-classified into 3 land cover classes:
  - `1` = Vegetation
  - `2` = Human-use
  - `3` = Other

### Kyushu_Reclassified_2019.tif
- Reclassified version of the 2019 raster
- Same 3 classes as above

### Pixel_Changes.tif
- Output from QGIS raster calculator
- Shows pixels that changed class between 2015 and 2019
