# BerkeleyDataBootcampProjectONE

#### notes
- ideally, we have data that has a dedicated ZIPCODE column (easier to merge)
- a STATE column is kept in the shorterdf file for easier visualization purposes as we can just use pandas to filter for a state or two and see what things look like on a smaller scale

#### sources so far
- [money data](https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics-2020-zip-code-data-soi)
- [zip conversion](https://simplemaps.com/data/us-zips)
- [health data](https://chronicdata.cdc.gov/500-Cities-Places/PLACES-ZCTA-Data-GIS-Friendly-Format-2022-release/kee5-23sr)
	- note: zcta != zip, but most of the time they're close enough for them to be interexchangeable. also, they are estimates (rigorous, but estimates nonetheless) made through the CDC PLACES project's specific methodologies.
- [ssa data](https://www.ssa.gov/policy/docs/statcomps/oasdi_zip/2020/index.html)