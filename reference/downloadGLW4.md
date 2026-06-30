# downloadGLW4

Downloads Gridded Livestock of the World version 4 (GLW 4) raster data
for reference years 2015 (Harvard Dataverse) and 2020 (FAO GIS Manager).
Eight livestock species are available for 2015 (dasymetric and areal
weighting); six species for 2020 (dasymetric only). Source catalogues:
https://dataverse.harvard.edu/dataverse/glw_4
https://data.apps.fao.org/catalog/iso/9d1e149b-d63f-4213-978b-317a8eb42d02

## Usage

``` r
downloadGLW4(subtype = "Da_Ct_2015")
```

## Arguments

- subtype:

  Weighting method, livestock species, and reference year separated by
  underscores (`"<method>_<species>_<year>"`). Available options:

  - 2015 – dasymetric (Da): `Da_Ct_2015`, `Da_Sh_2015`, `Da_Pg_2015`,
    `Da_Bf_2015`, `Da_Ch_2015`, `Da_Ho_2015`, `Da_Gt_2015`, `Da_Dk_2015`

  - 2015 – areal (Aw): `Aw_Ct_2015`, `Aw_Sh_2015`, `Aw_Pg_2015`,
    `Aw_Bf_2015`, `Aw_Ch_2015`, `Aw_Ho_2015`, `Aw_Gt_2015`, `Aw_Dk_2015`

  - 2020 – dasymetric (Da) only: `Da_Ct_2020`, `Da_Sh_2020`,
    `Da_Pg_2020`, `Da_Bf_2020`, `Da_Ch_2020`, `Da_Gt_2020`

## Value

A list with dataset metadata (url, doi, title, author, version,
release_date, unit, description, license).

## Author

Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
downloadSource("GLW4", subtype = "Da_Ct_2015")
downloadSource("GLW4", subtype = "Da_Ct_2020")
} # }
```
