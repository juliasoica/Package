
# Monte Carlo integration

Can integrate fucntions….

# Installation

``` r
devtools::install_github("juliasoica/Package")
```

# What it does

``` r
library(demo)
obj = mc_int(x_range = c(0,1), fun = "x^2*sin(x^2/pi)", B = 10^3)
plot(obj)
```

![](README_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->
