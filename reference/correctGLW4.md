# correctGLW4

Replaces NA values and any negative artefacts with zero in GLW 4 gridded
livestock rasters (reference years 2015 and 2020).

## Usage

``` r
correctGLW4(x)
```

## Arguments

- x:

  magpie object provided by the read function

## Value

Magpie object with NA and negative values replaced by 0.

## See also

[`readGLW4`](readGLW4.md)

## Author

Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
  readSource("GLW4", subtype = "Da_Ct_2015", convert = "onlycorrect")
} # }
```
