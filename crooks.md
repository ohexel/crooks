# Bivariate color scales
From Clause Wilke ([link](https://twitter.com/ClausWilke/status/1013302530095411200), see also [here](https://github.com/clauswilke/multiscales))

```{.R}
library(ggplot2)
library(multiscales)
library(colorspace)

ggplot(FL_house_values, aes(fill = zip(estimate/1000, moe/estimate))) + 
    geom_sf(color = "gray30", size = 0.2) + 
    coord_sf(xlim = c(-88, -79.8), ylim = c(24.1, 31.2), datum = NA) +
    bivariate_scale("fill",
        pal_carto_vsup(palette = "Sunset", rev = TRUE),
        name = c("median house\nvalues ($1K)", "uncertainty"),
        limits = list(c(0, 400), c(0, 0.4)),
        breaks = list(waiver(), c(0.05, 0.15, 0.25, 0.35)),
        labels = list(waiver(), scales::percent),
        guide = "colourbox"
    ) +
    theme_void() +
    theme(
        legend.key.size = grid::unit(0.8, "cm"),
        legend.title.align = 0.5,
        legend.justification = c(0,0),
        legend.position = c(0.1, 0.2)
    )
```
