## Background

Data providers and users need to have confidence in their data. I've found that within earth science this need has often been met by data providers developing bespoke, highly specific validation tools which are often not accessible to users. Deviations from standards and expectations (i.e., data quirks) still slip through the cracks, leading to a status quo for downstream users of designing pipelines that use the dataset and watching it fail part-way through, then debugging to find out why. Occasionally, there are technical documents accompanying datasets that describe known issues, but this isn't especially common. When these documents exist, they still require human reading and interpretation and may not be comprehensive.

ndquirk is a proposal for an extensible tool that quickly identifies quirks in N-dimensional datasets, where a 'quirk' is a deviation from a defined set of expectations.

## Goals
Primary goal
- Provide a accessible, extensible, and performant tool for identifying and communicating data deviations from a set of expectations for N-D datasets.

Sub-goals
- Provide simple mechanisms to run validation proximal to the data.
- Provide mechanisms for distributed data validation.
- Leverage existing software and validators whenever possible.
- Minimize as much as possible the number of get requests and amount of data transferred during data validation.
- Provide simple storage option configuration (i.e., no pass-through kwargs).
- Provide simple run-time configuration.
- Provide accessible documentation and demonstrations for all common use cases.
- Maintain 100% coverage in testing utilities.

## Partner and Stakeholders

This utility would be relevant for any data provider or user of N-D data.

This proposal has grown from many conversations over the years, all of whom would be likely stakeholders in the project. These people include:

- @abarciauskas-bgse
- @sharkinsspatial
- @jhamman
- @norlandrhagen
- @rabernat
- @briannapagan
- @andersy005
- @eni-awowale
- @omshinde

## Milestones

- [ ] Define project goals
    - [ ] Construct a list of use cases for the library
	- [ ] Define stakeholders and communication pathways for soliciting feedback
- [ ] Complete an API design document, including establishing whether a new library is necessary or an extension for great expectations would be sufficient
- [ ] Implement a mechanism for defining and connecting to a data source
- [ ] Implement, test, and document mechanisms for defining expectations
	- [ ] Demonstrate defining data format expectation (e.g., Cloud-Optimized GeoTIFF)
		- [ ] Define mechanisms for versioning data and metadata formats expectations
	- [ ] Demonstrate defining a chunk schema expectation (e.g., constant chunk sizes)
	- [ ] Demonstrate defining an encoding expectation (e.g., entirely zlib compression)
	- [ ] Demonstrate defining metadata standards (e.g., CF, Croissant)
	- [ ] Demonstrate defining data hierarchy expectations (e.g., Dataset vs. DataTree)
	- [ ] Demonstrate defining data type expectations (e.g., all float64)
	- [ ] Demonstrate defining data value expectations (e.g., no NaNs)
- [ ] Demonstrate validating expectations in parallel
- [ ] Demonstrate running the expectations using data proximate computing
- [ ] Demonstrate building a browser-based UI for defining and validating expectations

### Resources

- [https://github.com/great-expectations/great_expectations/issues/1942](https://github.com/great-expectations/great_expectations/issues/1942)
- [https://cfchecker.ncas.ac.uk/](https://cfchecker.ncas.ac.uk/)
- [https://github.com/zarr-developers/pydantic-zarr](https://github.com/zarr-developers/pydantic-zarr)
- [https://discourse.pangeo.io/t/tool-for-validating-geo-data-services-moved-to-the-cloud/4118](https://discourse.pangeo.io/t/tool-for-validating-geo-data-services-moved-to-the-cloud/4118)
- [https://github.com/briannapagan/quirky-data-checker](https://github.com/briannapagan/quirky-data-checker)
- [https://www.earthdata.nasa.gov/learn/earth-observation-data-basics/data-maturity-levels](https://www.earthdata.nasa.gov/learn/earth-observation-data-basics/data-maturity-levels)
- [https://agupubs.onlinelibrary.wiley.com/doi/full/10.1002/2017RG000562](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1002/2017RG000562)
- [https://www.earthdata.nasa.gov/about/competitive-programs/access/data-quality-screening-service](https://www.earthdata.nasa.gov/about/competitive-programs/access/data-quality-screening-service)
- [https://podaac-tools.jpl.nasa.gov/mcc/](https://podaac-tools.jpl.nasa.gov/mcc/)
- [https://wiki.earthdata.nasa.gov/display/ESDSWG/Dataset+Interoperability+Recommendations+for+Earth+Science](https://wiki.earthdata.nasa.gov/display/ESDSWG/Dataset+Interoperability+Recommendations+for+Earth+Science)
- [https://github.com/xarray-contrib/xarray-schema](https://github.com/xarray-contrib/xarray-schema)