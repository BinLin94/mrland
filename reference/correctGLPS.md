# correctGLPS

Replaces NA values and negative artefacts with zero for monogastric
subtypes (chickens and pigs). Ruminant_2000 categorical data is left
unchanged as 0 is not a valid LPS class.

## Usage

``` r
correctGLPS(x, subtype)
```

## Arguments

- x:

  magpie object provided by the read function

- subtype:

  subtype string passed from readSource

## Value

Magpie object with NA and negative values replaced by 0 for monogastric
subtypes; unchanged for Ruminant_2000.

## See also

[`readGLPS`](readGLPS.md)

## Author

Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
  readSource("GLPS", subtype = "Ch_Ext_2010", convert = "onlycorrect")
} # }
```
