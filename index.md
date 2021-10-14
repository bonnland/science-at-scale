# DRAFT:  Landing Page for CESM DART Reanalysis Data on AWS


# Overview


# Accessing CESM DART Data on AWS


- S3 bucket name: **ncar-dart-cam6**
- Region: **us-west-2** region
- Amazon resource name: **arn:aws:s3:::ncar-dart-cam6**
- Bucket contents list: https://ncar-dart-cam6.s3.amazonaws.com/



# Data


# Notebook Examples


# Data Citation

## Data Catalog

The table below shows the available Zarr stores, including the experiments, variables, time ranges, and 2D or 3D nature (3D means multiple atmosphere levels).

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

# Contact

Data are freely available and reusable under the terms of the CC-BY-4.0 license. See Terms of Use. If you use these data, we request that you provide attribution in any derived products. The original, complete LENS dataset and the AWS-hosted subset have different DOIs (Digital Object Identifiers) to reflect their differing scope and format


You can use the [editor on GitHub](https://github.com/bonnland/science-at-scale/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
