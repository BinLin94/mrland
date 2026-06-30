# readGLW3

Reads Gridded Livestock of the World version 3 (GLW 3) raster data for
reference year 2010, downloaded from Harvard Dataverse. Eight livestock
species are available with both dasymetric and areal weighting. Source
catalogue:
https://www.fao.org/livestock-systems/global-distributions/en/

## Usage

``` r
readGLW3(subtype = "Da_Ct_2010")
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

A gridded magpie object with gridded livestock of the world

## Author

Marcos Alves, Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
readSource("GLW3", subtype = "Da_Ct_2010", convert = FALSE)
} # }
```
