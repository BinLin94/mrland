# correctGLW3

Replaces NA values and any negative artefacts with zero in GLW 3 gridded
livestock rasters (reference year 2010).

## Usage

``` r
correctGLW3(x)
```

## Arguments

- x:

  magpie object provided by the read function

## Value

Magpie object with NA and negative values replaced by 0.

## See also

[`readGLW3`](readGLW3.md)

## Author

Marcos Alves, Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
  readSource("GLW3", subtype = "Da_Ct_2010", convert = "onlycorrect")
} # }
```
