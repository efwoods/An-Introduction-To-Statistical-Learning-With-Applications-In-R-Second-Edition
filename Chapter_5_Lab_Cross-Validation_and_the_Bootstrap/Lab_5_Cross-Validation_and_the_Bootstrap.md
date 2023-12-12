Lab 5 Cross-Validation and the Bootstrap
================
Evan Woods
2023-12-12

## The Validation Set Approach

``` r
# Selects 196 random numbers which range from 1 to 392
  train <- sample(392, 196) 
```

``` r
  lm.fit <- lm(mpg ~ horsepower, data = Auto, subset = train)
```

``` r
# The estimated test mean squared error for the linear regression fit. 
mean((mpg - predict(lm.fit, Auto))[-train]^2) 
```

    [1] 23.26601

``` r
lm.fit2 <- lm(mpg ~ poly(horsepower, 2), data = Auto, subset = train)
mean((mpg - predict(lm.fit2, Auto))[-train]^2)
```

    [1] 18.71646

``` r
lm.fit3 <- lm(mpg ~ poly(horsepower, 3), data = Auto, subset = train)
mean((mpg - predict(lm.fit3, Auto))[-train]^2)
```

    [1] 18.79401
