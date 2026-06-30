# readGLW4

reads in Gridded Livestock of the World v4, downloaded from:
https://dataverse.harvard.edu/dataverse/glw_4 (2015) and
https://data.apps.fao.org/catalog/iso/9d1e149b-d63f-4213-978b-317a8eb42d02
(2020)

## Usage

``` r
readGLW4(subtype = "Da_Ct_2015")
```

## Arguments

- subtype:

  Weighting method, livestock species, and reference year
  (`"<method>_<species>_<year>"`):

  - Da: Dasymetric weighting informed by Random Forest

  - Aw: Areal weighting – 2015 only

    - `Ch`: Chicken

    - `Ct`: Cattle

    - `Pg`: Pigs

    - `Sh`: Sheep

    - `Gt`: Goats

    - `Ho`: Horse (2015 only)

    - `Dk`: Ducks (2015 only)

    - `Bf`: Buffaloes

## Value

A gridded magpie object with gridded livestock counts. 2015 data: heads
per 0.5-degree pixel (aggregated by sum). 2020 data: heads per km2
(aggregated by mean, native density unit).

## Author

David M Chen, Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
readSource("GLW4", subtype = "Da_Ct_2015", convert = FALSE)
readSource("GLW4", subtype = "Da_Ct_2020", convert = FALSE)
} # }
```
