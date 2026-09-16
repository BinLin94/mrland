# readGLW3all

Reads Gridded Livestock of the World version 3 (GLW 3) raster data for
reference year 2010, downloaded from Harvard Dataverse. Eight livestock
species are available with both dasymetric and areal weighting. Source
catalogue:
https://www.fao.org/livestock-systems/global-distributions/en/

## Usage

``` r
readGLW3all(subtype = "Da_Ct_2010")
```

## Arguments

- subtype:

  Weighting method, livestock species, and reference year
  (`"<method>_<species>_2010"`):

  - Da: Dasymetric weighting informed by Random Forest

  - Aw: Areal weighting (distributed uniformly in each census unit)

    - `Ct`: Cattle

    - `Sh`: Sheep

    - `Pg`: Pigs

    - `Bf`: Buffaloes

    - `Ch`: Chickens

    - `Ho`: Horses

    - `Gt`: Goats

    - `Dk`: Ducks

## Value

A magpie object with 67420 lpjcell coordinates, one year (y2010), and
gridded livestock counts in heads per 0.5-degree pixel.

## See also

[`readGLW3`](readGLW3.md), [`correctGLW3all`](correctGLW3all.md)

## Author

Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
readSource("GLW3all", subtype = "Da_Ct_2010", convert = FALSE)
} # }
```
