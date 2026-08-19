# calcLivestockDistribution

Calculates gridded livestock distribution by species using GLW3/GLW4
spatial snapshots (2010, 2015, 2020) linearly interpolated to requested
FAO years, with constant extrapolation beyond the anchor range. Country
totals come from `calcAnimalStocks`. Eight species are covered: cattle
(Ct), buffaloes (Bf), sheep (Sh), goats (Gt), horses (Ho), pigs (Pg),
chickens (Ch), ducks (Dk). Horses and ducks are not available in GLW4
2020 and fall back to the 2015 spatial distribution.

Monogastrics (Pg, Ch, Dk) fall back to total land area (all nine land
classes summed) for countries where GLW has zero grid signal - about 70
countries per product, mostly small island states with no satellite
pixel coverage. This recovers countries that have any land recorded at
all (e.g. WSM, TON) but not micro-states whose total land area is itself
~0 at 0.5-degree resolution (e.g. KIR, TUV, NRU, NIU, COK, SYC, FSM,
PYF) - for those, no land-based proxy of any kind has anything to fall
back to, since the country doesn't register a meaningful land footprint
in the underlying cellular land-use data at all. This is a
grid-resolution limit (like Macau having no grid cell of its own), not
something this function's fallback logic can resolve.

## Usage

``` r
calcLivestockDistribution(
  output = "head",
  landProxy = "speciesSpecific",
  category = "magpie",
  selectyears = paste0("y", 1961:2025)
)
```

## Arguments

- output:

  Type of output:

  - `"weight"`: dimensionless spatial downscaling weight within each
    country (sums to 1 per country per category per year).

  - `"head"`: absolute livestock numbers (Million animals per grid
    cell).

  - `"density"`: livestock per land area (Million animals per Mha). For
    ruminants, the denominator is the pasture/rangeland proxy area
    controlled by `landProxy`. For monogastrics (Pg, Ch, Dk), total
    grid-cell land area is used as the denominator.

- landProxy:

  Land proxy controlling spatial allocation for ruminants only.
  Monogastrics always use fixed GLW spatial shares regardless of this
  setting:

  - `"glw"`: all categories use fixed GLW spatial shares; no land data
    used.

  - `"pastRange"`: ruminants (Ct, Bf, Sh, Gt, Ho) scaled by combined
    managed pasture and rangeland (`past + range`).

  - `"speciesSpecific"`: cattle/buffalo (Ct, Bf) scaled by managed
    pasture (`past`); sheep/goats/horses (Sh, Gt, Ho) scaled by
    rangeland (`range`).

- category:

  Livestock category classification for output:

  - `"FAO"` (default): eight FAO/GLW species (Ct, Bf, Sh, Gt, Ho, Pg,
    Ch, Dk).

  - `"magpie"`: five MAgPIE livestock categories (livst_rum, livst_milk,
    livst_pig, livst_chick, livst_egg). FAO species are computed first
    and then aggregated using national dairy/broiler fractions from
    `calcAnimalStocks`.

- selectyears:

  Years to compute. Intersected with available FAO years.

## Value

A list with elements: `x` (magpie object at lpjcell resolution, 67420
cells), `weight` (NULL), `unit` (character), `description` (character),
and `isocountries` (FALSE — data is cellular, not country-level).

## Author

Bin Lin

## Examples

``` r
if (FALSE) { # \dontrun{
calcOutput("LivestockDistribution", output = "weight", aggregate = FALSE)
calcOutput("LivestockDistribution", output = "head",   aggregate = FALSE)
calcOutput("LivestockDistribution", output = "density", landProxy = "speciesSpecific",
           aggregate = FALSE)
calcOutput("LivestockDistribution", category = "magpie", aggregate = FALSE)
} # }
```
