# Kyushu-Land-Cover-2015-2019
This project analyzed land cover change in the Kyushu region of Japan using classified raster data from the Copernicus Land Monitoring Service. Both QGIS and Python were used to process and visualize the changes in ‘vegetation’, ‘human-use’, and ‘others’ land classes.

## Data Sources:
- Copernicus Global Land Cover (raster 100m):
   - 2015: https://land.copernicus.eu/en/products/global-dynamic-land-cover/copernicus-global-land-service-land-cover-100m-collection-3-epoch-2015-globe#download
   - 2019: https://land.copernicus.eu/en/products/global-dynamic-land-cover/copernicus-global-land-service-land-cover-100m-collection-3-epoch-2019-globe#download
- GADM: https://gadm.org/download_country.html

## Tools used:
- QGIS (Dissolve, Clip Raster by Mask Layer, Reclassify by Table, Raster Layer Unique Values Report)
- Python (Rasterio, Numpy, Matplotlib)

## Steps:
### Data Acquisition:
- Downloaded Global Dynamic Land Cover raster data (2015 and 2019) from the Copernicus Land Monitoring Service
- Downloaded GADM shapefiles for Japan to extract prefectural boundaries
### QGIS Processing
- Dissolved the GADM shapefiles to get Kyushu boundaries
- Clipped Raster by Mask Layer to isolate the raster data of only the Kyushu region
- Re-classified the raster into classes based on the map codes in Table 4 of the product user manual
  - Vegetation: 20, 30, 100, 111-116, 121-126
  - Human-use (urban, croplands): 40, 50
  - Others (bare, snow/ice, water bodies): 60, 70, 80, 90
  - Open Sea (Not included in the investigation): 200
- Used the Raster Layer Unique Values Report tool to find the pixel count for each class
- Converted the pixel counts into areas based on the resolution of the raster data: area (km²) = pixels × 0.01
- Used Raster Calculator to map pixels that have changed values between 2015 and 2019
### Python Analysis
- Used Python (numpy, matplotlib) to calculate the difference in area of each class between 2015 and 2019, then plot the changes as a bar graph
- Validated the results using Python (rasterio) to process the changes directly from the re-classified TIFF files

## Outputs:
- 3 maps:
  - Land classes in 2015
  - Land classes in 2019
  - Pixels that changed classes from 2015 to 2019
- 2 bar graphs showing the changes in area for each class:
  - One based on the QGIS raster report
  - One based on Python (rasterio) analysis
- A Jupyter Notebook containing the Python code used for analysis

## Notes:
- Large raster files are not provided here. Please download them from the links provided.
- This project is licensed under the MIT License.


