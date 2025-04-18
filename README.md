# height_correction_SAR_altimetry
This repository contains the NetCDF files used in the analysis presented in the manuscript:

    "Slope correction for ocean SAR altimetry"
    Authors: Juliette Gamot, Marie-Isabelle Pujol, Philippe Schaeffer and François Bignalet-Cazalet 
    Corresponding author: jgamot@groupcls.com


These datasets allow reproduction of the key results and figures in the manuscript. All data are provided in NetCDF-4 format and follow CF-1.8 conventions.

------------------------------------------------------------
Download the datasets
------------------------------------------------------------

The NetCDF files used in this study can be downloaded from the GitHub Release:

https://github.com/JulietteGamot/height_correction_SAR_altimetry/releases/tag/v1.0

This includes:

- ssha_S6A_SAR.nc
- ssha_J3_LRM.nc
- height_correction_S6A_SAR.nc

------------------------------------------------------------
File descriptions
------------------------------------------------------------

1. **ssha_S6A_SAR.nc**

    - Description: Along-track Sea Surface Height Anomaly (SSHA) from Sentinel-6A SAR altimeter, interpolated on theoretical tracks.
    - Dimensions: (cycle, track, point) = (40, 254, 3127)
    - Coordinates: Longitude and latitude are fixed theoretical tracks.
    - Temporal dimension ('cycle'): Represents the first 40 successive 10-day altimeter cycles of the Sentinel-6A mission.
    - Units: meters
    - Purpose: Provides gridded SSHA values for Sentinel-6A SAR altimetry.

2. **ssha_J3_LRM.nc**

    - Description: Along-track Sea Surface Height Anomaly (SSHA) from Jason-3 LRM altimeter, interpolated on the same theoretical grid.
    - Dimensions: (cycle, track, point) = (40, 254, 3127)
    - Coordinates: Identical to the Sentinel-6A grid.
    - Temporal dimension ('cycle'): Represents the 40 corresponding 10-day altimeter cycles from the Jason-3 mission.
    - Units: meters
    - Purpose: Enables direct comparison between Jason-3 and Sentinel-6A altimetric data on a common spatiotemporal basis.

3. **height_correction_S6A_SAR.nc**

    - Description: Height correction for SAR altimetry developed in the manuscript and applied to the Sentinel-6A theoretical grid.
    - Dimensions: (track, point) = (254, 3127)
    - Coordinates: Same theoretical longitude and latitude as above.
    - Units: meters
    - Purpose: Used to correct the Sentinel-6A SAR SSHA values for the sea surface slope effect.

------------------------------------------------------------
Conventions and Metadata
------------------------------------------------------------

All files follow CF-1.8 metadata conventions and include standard coordinate and variable attributes.

Please refer to the `ncdump -h` header of each file for complete metadata details.

------------------------------------------------------------
Reproducibility
------------------------------------------------------------

To reproduce the figures and results presented in the manuscript:

1. Use the SSHA files to compute mean sea level fields and inter-mission comparisons.
2. Apply the `height_correction_S6A_SAR.nc` values to the `ssha_S6A_SAR.nc` data, averaged over cycles.
