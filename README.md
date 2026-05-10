# Growing Season Length, Eastern North America

## Project Description
This map displays the growing season length (GSL) across eastern North America during 1981-2014. 
GSL is computed as the number of days between spring onset (SOS) and fall senescence (end of season, EOS). 
The map reveals a clear latitudinal gradient: shorter growing seasons at higher latitudes and elevations, 
longer growing seasons at lower latitudes. This pattern reflects fundamental biogeographic constraints on vegetation phenology.

## Data Source
- **EVI2 index from MODIS and AVHRR** (VIPPHEN product, Collection 6.1)
- **Time period:** 1981-2014 (decadal mean)
- **Spatial resolution:** 0.05 degrees (approximately 5.6 km)
- **Extent:** Eastern North America (east of 100°W, 13°N to 82°N)
- **Data availability:** [VIPPHEN Project at USGS](https://www.earthdata.nasa.gov/data/catalog/lpcloud-vipphen-evi2-004)

## Why This Map
Growing season length is a key metric for understanding how climate constrains vegetation productivity. By mapping GSL across a large latitudinal gradient, this project visualizes how day length and temperature decrease northward, compressing the window of time available for plant growth. This pattern supports Hopkins' Bioclimatic Law, which predicts phenological delays at higher latitudes and elevations.

## Methodology
The following steps were used to create this map:

1. **Data retrieval:** Retrieved end-of-season (EOS) and spring-onset (SOS) rasters for each year from 1981 to 2014 from the MODIS & AVHRR EVI2 archive (VIPPHEN product).

2. **GSL computation:** For each pixel and year, computed growing season length as: GSL = EOS - SOS (measured in days from January 1).

3. **Decadal aggregation:** Calculated the mean GSL across all 34 years (1981-2014) using the `terra::app()` function in R.

4. **Spatial reference:** All data retained in WGS84 (EPSG:4326).

5. **Visualization:** Imported the mean GSL raster into QGIS, applied a sequential color ramp (yellow to green) to highlight the latitudinal gradient, and added cartographic elements (legend, scale bar, north arrow, metadata).

**Software used:** R (terra package for raster processing), QGIS (for map design and export)

## Projections
- **Input projection:** WGS84 (EPSG:4326)
- **Output projection:** WGS84 (EPSG:4326)
- **Datum:** WGS84

## Map Interpretation
- **Yellow regions:** Short growing seasons, typically 100-150 days (high latitude, boreal/subarctic zones)
- **Green regions:** Long growing seasons, typically 200-280 days (low latitude, temperate/subtropical zones)

The gradient is driven primarily by latitude (which controls day length and temperature) and secondarily by elevation 
(which decreases temperature with altitude). Higher elevations show shorter GSL even at lower latitudes.

## Files in This Repository
- `index.html` - Main map display page
- `README.md` - This file
- `images/GSL_MAP671_1200.jpeg` - Web-resolution map (for viewing on the website)
- `images/GSL_MAP671_3000.jpeg` - High-resolution map (for downloading and printing)

## License
This project is licensed under the GNU General Public License v3.0. See LICENSE file for details.