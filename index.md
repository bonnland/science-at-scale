## CAM6 Data Assimilation Research Testbed (DART) Reanalysis Cloud-Optimized Dataset


## Overview

This is a cloud-hosted subset of the CAM6 Data Assimilation Research Testbed (DART) Reanalysis dataset. These data products are designed to facilitate a broad variety of research using NCAR's CESM2 models, ranging from model evaluation to (ensemble) hindcasting, data assimilation experiments, and sensitivity studies. They come from an 80 member ensemble reanalysis of the global troposphere and stratosphere using DART and CAM6 from CESM2.1. The data products represent the actual states of the atmosphere from 2011 through 2020 at a 1 degree horizontal resolution and 6 hourly frequency. Each ensemble member is an equally likely description of the atmosphere, and is also consistent with dynamics and physics of CAM6. This  dataset is derived from the "CAM6 Data Assimilation Research Testbed (DART) Reanalysis", DOI:10.5065/JG1E-8525


## Accessing CESM DART Data on AWS

- S3 bucket name: **ncar-dart-cam6**
- Region: **us-west-2** region
- Amazon resource name: **arn:aws:s3:::ncar-dart-cam6**
- Bucket contents list: https://ncar-dart-cam6.s3.amazonaws.com/

## Data

### Zarr format

The LENS data on AWS are structured according to the Zarr storage format. There are independent Zarr stores for each time frequency/variable combination. The naming convention is: {frequency}/{variable}.zarr where:

- frequency = weekly or hourly6
- variable = one of the variable names listed in the table below.

The table shows available Zarr stores, including the variables, time ranges, and 2D or 3D nature (3D means multiple atmosphere levels).

|variable|long_name|units|standard_name|vertical_levels|component|spatial_domain|start_time|end_time|frequency|path|
|--------|---------|-----|-------------|---------------|---------|--------------|----------|--------|---------|----|
|HR|total heterotrophic respiration|g/m^2/s|surface_upward_mass_flux_of_carbon_dioxide_expressed_as_carbon_due_to_heterotrophic_respiration|1|lnd|global|2012-01-01T06:00:00|2019-12-31T18:00:00|hourly6|s3://ncar-dart-cam6/hourly6/HR.zarr|
|TSA|2m air temperature|K|air_temperature|1|lnd|global|2012-01-01T06:00:00|2019-12-31T18:00:00|hourly6|s3://ncar-dart-cam6/hourly6/TSA.zarr|
|EFLX_LH_TOT|total latent heat flux [+ to atm]|W/m^2|surface_upward_latent_heat_flux|1|lnd|global|2012-01-01T06:00:00|2019-12-31T18:00:00|hourly6|s3://ncar-dart-cam6/hourly6/EFLX_LH_TOT.zarr|
|ER|total ecosystem respiration, autotrophic + heterotrophic|g/m^2/s|surface_upward_mass_flux_of_carbon_dioxide_expressed_as_carbon_due_to_total_ecosystem_respiration|1|lnd|global|2012-01-01T06:00:00|2019-12-31T18:00:00|hourly6|s3://ncar-dart-cam6/hourly6/ER.zarr|
|VS|Meridional wind, staggered|m/s|northward_wind|32|atm|global|2011-01-03T00:00:00|2019-12-30T00:00:00|weekly|s3://ncar-dart-cam6/weekly/VS.zarr|
|PS|Surface pressure|Pa|surface_air_pressure|1|atm|global|2011-01-03T00:00:00|2019-12-30T00:00:00|weekly|s3://ncar-dart-cam6/weekly/PS.zarr|
|Q|Specific humidity|kg/kg|specific_humidity|32|atm|global|2011-01-03T00:00:00|2019-12-30T00:00:00|weekly|s3://ncar-dart-cam6/weekly/Q.zarr|
|US|Zonal wind, staggered|m/s|eastward_wind|32|atm|global|2011-01-03T00:00:00|2019-12-30T00:00:00|weekly|s3://ncar-dart-cam6/weekly/US.zarr|
|CLDICE|Grid box averaged cloud ice amount|kg/kg|mass_fraction_of_cloud_ice_in_air|32|atm|global|2011-01-03T00:00:00|2019-12-30T00:00:00|weekly|s3://ncar-dart-cam6/weekly/CLDICE.zarr|
|T|Temperature|K|air_temperature|32|atm|global|2011-01-03T00:00:00|2019-12-30T00:00:00|weekly|s3://ncar-dart-cam6/weekly/T.zarr|
|CLDLIQ|Grid box averaged cloud liquid amount|kg/kg|mass_fraction_of_cloud_liquid_water_in_air|32|atm|global|2011-01-03T00:00:00|2019-12-30T00:00:00|weekly|s3://ncar-dart-cam6/weekly/CLDLIQ.zarr|


### Data Characteristics

(KR)

## Notebook Examples

- Jupyter Notebook creating a spaghetti plot of ensemble member values for any chosen variable, written in Python:  
  http://ncar-aws-www.s3-website-us-west-2.amazonaws.com/plot-diagnostics.v1.html

## Data Citation

- Cloud Copy ref
- Source (derived from) dataset ref
- Any pub/paper refs (KR)
- DART sfw citation (KR)

## Contact

Data are freely available and reusable under the terms of the CC-BY-4.0 license. See Terms of Use. If you use these data, we request that you provide attribution in any derived products. The original, complete DART Reanalysis dataset and the AWS-hosted subset have different DOIs (Digital Object Identifiers) to reflect their differing scope and format.

