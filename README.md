# Water Recognition Indices

# Purpose

This plugin was developed in order to automate water indices calculation on Tiff images as well as to apply a reclassification process on the generated image based on a threshold (defined by the user).

# Input and Outputs

Depending on the case you can have:

# Input

- Tiff image with the **required bands** to calculate the desired index.
- Tiff image with a water recognition index (NDVI, NDWI, etc) already applied.

# Output

- Tiff image with a water recognition index applied
- Tiff image reclassified based on defined threshold

# Usage

The plugins consists on a simple GUI to select the desired water recognition index or threshold you want to calculate on your raster image following the next steps:

1. Select the input raster image
2. Select the checkboxes for the indices you want to apply on the input image and/or the threshold for reclassification
3. If you select custom threshold value for any of the indices you can use the spin widget to increase or decrease this value
4. Select an output folder path where the generated images will be saved (if you leave this filed empty the images will be generated as temporary layers which you can export later)
5. Click the run button to start the process

# Example

# Satellite image with no index applied

- In this example we will apply NDVI and WRI water recognition indices to a Landsat 8 image (downloaded from Google Earth Engine) and also apply a reclassification threshold on the generated image.
- You can use the **Huallaga_no_index.tif** image provided in the github reporsitory or any other multiband image

1. Open the image on QGIS by dragging the image to the layers panel
2. Go to **Raster** menu and select the **Water Recognition Indices** option and select the plugin
3. Select the raster input in the combobox
4. Select the NDVI and WRI options as well as the custom threshold options for these indices
5. Change the value for the NDVI threshold to 0.1 and the WRI threshold to 1.0 (these values are just for testing the reclassification process)
6. Select the output folder by clicking the **...** button in the _Select output folder_ section of the plugin
7. Click the **Run** button and wait for the process to finish
8. As a result we have 4 generated images (2 for each water recognition index and 2 for each threshold reclassification) named according to their corresponding index and/or threshold value saved on the select output folder.

# Satellite image previous index applied

- In this example we will apply a reclassification process to a Landsat 8 image (downloaded from Google Earth Engine) with NDVI index already applied.
- You can use the **Huallaga_NDVI.tif** image provided in the github reporsitory or any other image with index applied

1. Open the image on QGIS by dragging the image to the layers panel
2. Go to **Raster** menu and select the **Water Recognition Indices** option and select the plugin
3. Select the raster input in the combobox
4. Select **only** the **Custom NDVI threshold** option
5. Change the value for the NDVI threshold to 0.1 (this value is just for testing the reclassification process)
6. Select the output folder by clicking the **...** button in the _Select output folder_ section of the plugin
7. Click the **Run** button and wait for the process to finish
8. As a result we have a reclassified image named according to the corresponding threshold value saved on the select output folder.

Notice that we could have selected any other index or threshold option for this example, but since the image had the NDVI index already applied it wouldn't make much sense to apply NDWI or WRI index calculation and/or followed by a reclassification step.

# Notes

- This plugin works for Landsat collection images (namely Landsat 5, 7 and 8) for the time being. We plan on add more satellite imagery options, such as Sentinel, for indices calculation in the future.
- The threshold field can have any numeric value you choose, but take in account that these indices (in some cases) have some range values in which you can detect not only water but also vegetation, for example. Check the references section for more information about these range values.
- The plugin was tested on QGIS3 only, if you experience some compatibility issues please write to the contact emails provided in the contributors section for more support.

# References

# Contributors

- The idea and development for this plugin was conceived as part of a founded [River research project in the Peruvian Amazon](https://www.moore.org/grant-detail?grantId=GBMF7711) conducted by [CITA - UTEC](https://cita.utec.edu.pe/). Help us improve by testing, giving feedback on bugs and bringing new ideas for better performance. We really appreciate your help :) !
- Developed by: Gerardo Valencia Mesías, GIS Team CITA-UTEC
- Contact emails: gvalencia@utec.edu.pe | cita@utec.edu.pe
