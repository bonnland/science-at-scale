# CAM6 Data Assimilation Research Testbed (DART) Reanalysis Cloud-Optimized Dataset


## Overview

This is a cloud-hosted subset of the Community Atmosphere Model version 6 (CAM6) Data Assimilation Research Testbed (DART) Reanalysis dataset. These data products are designed to facilitate a broad variety of research using the National Center for Atmospheric Research's Community Earth System Model (NCAR CESM), ranging from model evaluation to (ensemble) hindcasting, data assimilation experiments, and sensitivity studies. They come from an 80 member ensemble reanalysis of the global troposphere and stratosphere using DART and CAM6 from CESM2.1. The data products represent the actual states of the atmosphere from 2011 through 2020 at a 1 degree horizontal resolution and 6 hourly frequency. Each ensemble member is an equally likely description of the atmosphere, and is also consistent with dynamics and physics of CAM6. This dataset is derived from the "CAM6 Data Assimilation Research Testbed (DART) Reanalysis", [DOI:10.5065/JG1E-8525](https://doi.org/10.5065/JG1E-8525).

## Accessing CESM DART Data on AWS

- S3 bucket name: **ncar-dart-cam6**
- Region: **us-west-2** region
- Amazon resource name: **arn:aws:s3:::ncar-dart-cam6**
- Bucket contents list: https://ncar-dart-cam6.s3.amazonaws.com/


## Data Characteristics

- Variables (PS, T, US, VS, Q, CLDLIQ, CLDICE) are atmospheric fields available from each ensemble member of the Community Atmosphere Model (CAM6).  They provide weekly context for the other, more frequent, plant growth variables (ER, HR, TSA, EFLX_LH_TOT), which come from the Community Land Model component of CESM.  Ensemble member 1 of both the atmospheric and land variables were written from member 1 of the assimilation, and so forth for each member.  
- Depending on user interest, we may add more plant growth variables which include Plant Functional Type (PFT) information 
(GPP, GRAINC_TO_FOOD, GSSHALN, GSSUNLN, NPP, NPP_NUPTAKE, PLANT_NDEMAND, QVEGT, TLAI). Please contact us at cisl-aws-lens@ucar.edu if you are interested in using the PFT data.


## Zarr format

The data on AWS are structured according to the Zarr storage format. There are independent Zarr stores for each time frequency/variable combination. The naming convention is: `{frequency}/{variable}.zarr` where:

- frequency = `weekly` or `hourly6`
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

## Notebook Examples

- Jupyter Notebook creating a spaghetti plot of ensemble member values for any chosen variable, written in Python:  
  https://github.com/NCAR/ncar-dart-cam6/blob/main/notebooks/plot-ensemble-values.ipynb

## Citations

- AWS-hosted subset: https://doi.org/10.26024/sprq-2d04 Bonnlander, B., and Raeder, K., (2019), “CAM6 Data Assimilation Research Testbed (DART) Reanalysis Cloud-Optimized Dataset,” UCAR/NCAR Computational and Informations Systems Lab
- Original dataset: https://doi.org/10.5065/JG1E-8525 Data Assimilation Research Section/Computational & Information Systems/National Center for Atmospheric Research/University Corporation for Atmospheric Research. 2020. CAM6 Data Assimilation Research Testbed (DART) Reanalysis. Research Data Archive at the National Center for Atmospheric Research, Computational and Information Systems Laboratory. https://doi.org/10.5065/JG1E-8525. Accessed 27 Oct 2021
- The Scientific Reports description of the Original dataset: https://doi.org/10.1038/s41598-021-92927-0 Raeder, K., Hoar, T.J., El Gharamti, M. et al (2021), "A new CAM6 + DART reanalysis with surface forcing from CAM6 to other CESM models", Sci Rep 11, 16384
- The DART Software: https://docs.dart.ucar.edu

## Contact

Data are freely available and reusable under the terms of the CC-BY-4.0 license. See Terms of Use. If you use these data, we request that you provide attribution in any derived products. The original, complete DART Reanalysis dataset and the AWS-hosted subset have different DOIs (Digital Object Identifiers) to reflect their differing scope and format.

If you have questions or want to submit a data request, please reach out to us on our [GitHub Discussions](https://github.com/NCAR/ncar-dart-cam6/issues) page or via email: cisl-aws-lens@ucar.edu.

