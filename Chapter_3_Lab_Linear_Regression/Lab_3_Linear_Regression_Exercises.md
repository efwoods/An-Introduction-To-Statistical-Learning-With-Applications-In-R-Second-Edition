Lab 3 Linear Regression Exercises
================
Evan Woods
2023-12-06

``` r
LoadLibraries <- function() {
  if(!require("MASS")) install.packages("MASS")
  if(!require("ISLR2")) install.packages("ISLR2`")

  library(MASS)
  library(ISLR2)
  print("Libraries have been loaded!")
}
```
