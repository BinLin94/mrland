# downloadGLPS

Downloads Global Livestock Production System (GLPS) data from Harvard
Dataverse. Three animal groups are available:

- Chickens (2010): backyard (extensive) and intensive management

- Pigs (2010): backyard (extensive), semi-intensive, and industrial

- Ruminants (ca. 2000): categorical production system map (LG/MR/MI
  classes), based on Global Land Cover 2000 (GLC2k)

Source catalogues:
https://www.fao.org/livestock-systems/production-systems/chicken/en/
https://www.fao.org/livestock-systems/production-systems/pig/en/
https://www.fao.org/livestock-systems/production-systems/ruminant/en/

## Usage

``` r
downloadGLPS(subtype = "Ch_Ext_2010")
```

## Arguments

- subtype:

  Animal group and management system. Available options:

  - Chicken – `Ch_Ext_2010` (backyard/extensive), `Ch_Int_2010`
    (intensive)

  - Pig – `Pg_Ext_2010` (backyard/extensive), `Pg_Int_2010`
    (semi-intensive), `Pg_Ind_2010` (industrial/intensive)

  - Ruminant – `Ruminant_2000` (categorical LPS raster ca. 2000:
    landless/LG, mixed rainfed/MR, mixed irrigated/MI classes)

## Value

A list with dataset metadata (url, doi, title, author, version,
release_date, unit, description, license, reference).

## Author

Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
downloadSource("GLPS", subtype = "Ch_Ext_2010")
downloadSource("GLPS", subtype = "Pg_Ind_2010")
downloadSource("GLPS", subtype = "Ruminant_2000")
} # }
```
