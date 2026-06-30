# readGLPS

Reads Global Livestock Production System (GLPS) data. Chicken and pig
subtypes are for reference year 2010; the ruminant subtype
(Ruminant_2000) is for reference year ca. 2000. Three animal groups are
available:

- Chickens: backyard (extensive) and intensive management – continuous
  density raster (heads/pixel)

- Pigs: backyard (extensive), semi-intensive, and industrial –
  continuous density raster (heads/pixel)

- Ruminants: categorical production system map (LPS class code per
  pixel; aggregated to 0.5 degree by modal value)

## Usage

``` r
readGLPS(subtype = "Ch_Ext_2010")
```

## Arguments

- subtype:

  Animal group and management system. Available options:

  - Chicken – `Ch_Ext_2010` (backyard/extensive), `Ch_Int_2010`
    (intensive)

  - Pig – `Pg_Ext_2010` (backyard/extensive), `Pg_Int_2010`
    (semi-intensive), `Pg_Ind_2010` (industrial/intensive)

  - Ruminant – `Ruminant_2000` (categorical LPS raster ca. 2000)

## Value

A gridded magpie object. Monogastric subtypes: heads/pixel.
Ruminant_2000: categorical LPS class code per pixel.

## Author

Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
readSource("GLPS", subtype = "Ch_Ext_2010", convert = FALSE)
readSource("GLPS", subtype = "Ruminant_2000", convert = FALSE)
} # }
```
