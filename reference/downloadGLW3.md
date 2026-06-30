# downloadGLW3

Downloads Gridded Livestock of the World version 3 (GLW 3) raster data
for reference year 2010 from Harvard Dataverse. Eight livestock species
are available with both dasymetric and areal weighting. Source
catalogue:
https://www.fao.org/livestock-systems/global-distributions/en/

## Usage

``` r
downloadGLW3(subtype = "Da_Ct_2010")
```

## Arguments

- subtype:

  Weighting method, livestock species, and reference year separated by
  underscores (`"<method>_<species>_2010"`). Available options:

  - Dasymetric (Da): `Da_Ct_2010`, `Da_Sh_2010`, `Da_Pg_2010`,
    `Da_Bf_2010`, `Da_Ch_2010`, `Da_Ho_2010`, `Da_Gt_2010`, `Da_Dk_2010`

  - Areal (Aw): `Aw_Ct_2010`, `Aw_Sh_2010`, `Aw_Pg_2010`, `Aw_Bf_2010`,
    `Aw_Ch_2010`, `Aw_Ho_2010`, `Aw_Gt_2010`, `Aw_Dk_2010`

## Value

A list with dataset metadata (url, doi, title, author, version,
release_date, unit, description, license, reference).

## Author

Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
downloadSource("GLW3", subtype = "Da_Ct_2010")
downloadSource("GLW3", subtype = "Aw_Sh_2010")
} # }
```
