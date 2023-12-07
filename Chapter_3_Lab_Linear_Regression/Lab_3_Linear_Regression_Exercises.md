Lab 3 Linear Regression Exercises
================
Evan Woods
2023-12-07

# §3.7 Exercises

<!-- ## Conceptual -->
<!-- ### Question 7: -->
<!-- ## Getting started with equations -->
<!-- We can write fractions: $\frac{2}{3}$. We can also handle things like estimated population growth rate, e.g., $\hat{\lambda}=1.02$. And, $\sqrt{4}=2$. -->
<!-- $$\alpha, \beta,  \gamma, \Gamma$$ -->
<!-- $$a \pm b$$ -->
<!-- $$x \ge 15$$ -->
<!-- $$a_i \ge 0~~~\forall i$$ -->
<!-- ## Matrix -->
<!-- $$A_{m,n} = -->
<!--  \begin{pmatrix} -->
<!--   a_{1,1} & a_{1,2} & \cdots & a_{1,n} \\ -->
<!--   a_{2,1} & a_{2,2} & \cdots & a_{2,n} \\ -->
<!--   \vdots  & \vdots  & \ddots & \vdots  \\ -->
<!--   a_{m,1} & a_{m,2} & \cdots & a_{m,n} -->
<!--  \end{pmatrix}$$ -->

## Applied

### Question 8:

This question involves the use of simple linear regression on the Auto
data set.

- **Question 8-a**:

  1.  Is there a relationship between the predictor and the response?
  2.  How strong is the relationship between the predictor and the
      response?
  3.  Is the relationship between the predictor and the response
      positive or negative?
  4.  What is the predicted mpg associated with a horsepower of 98? What
      are the associated 95% confidence and prediction intervals?

- **Answer**:

  1.  There is a relationship between the predictor and the response.
      The F-statistic is very high which indicates that at least one
      variable is a predictor of the response, and there is only one
      predictor.
  2.  The Residual Standard Error is 4.906. The mean value of the
      response, mpg, is 23.45. This indicates that the percentage of
      error of this model is high: 20.9%. The Adjusted R<sup>2</sup> is
      60.49. This indicatest that 60.49% of the variability present in
      the data is captured by the model. This is a weak model.
  3.  There is a negative relationship between the predictor and the
      response. This is observable from the negative coefficient of
      horsepower.
  4.  The predicted mpg associated with a horsepower of 98 is 24.47 mpg.
      The confidence interval is 23.97 to 24.96. The prediction interval
      is 14.8 to 34.12.

``` r
lm.fit <- lm(mpg ~ horsepower)

# Calculating Percentage of Error from Residual Standard Error
mean_value_of_response <- mean(mpg)
mean_value_of_response
```

    [1] 23.44592

``` r
RSE <- summary.lm(lm.fit)$sigma

percentage_of_error <- (RSE / mean(mpg)) * 100
percentage_of_error
```

    [1] 20.92371

``` r
# Summary Statistics
summary.lm(lm.fit)
```


    Call:
    lm(formula = mpg ~ horsepower)

    Residuals:
         Min       1Q   Median       3Q      Max 
    -13.5710  -3.2592  -0.3435   2.7630  16.9240 

    Coefficients:
                 Estimate Std. Error t value Pr(>|t|)    
    (Intercept) 39.935861   0.717499   55.66   <2e-16 ***
    horsepower  -0.157845   0.006446  -24.49   <2e-16 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 4.906 on 390 degrees of freedom
    Multiple R-squared:  0.6059,    Adjusted R-squared:  0.6049 
    F-statistic: 599.7 on 1 and 390 DF,  p-value: < 2.2e-16

``` r
# Prediction & Confidence Intervals
predict(lm.fit, data.frame(horsepower = c(98)), interval = "prediction")
```

           fit     lwr      upr
    1 24.46708 14.8094 34.12476

``` r
predict(lm.fit, data.frame(horsepower = c(98)), interval = "confidence")
```

           fit      lwr      upr
    1 24.46708 23.97308 24.96108

- **Question 8-b**: Plot the response and the predictor. Use the
  abline() function to display the least squares regression line.
  - **Answer**:

<img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-8-1.png" width="70%" style="display: block; margin: auto;" />

- **Question 8-c**: Use the plot() function to produce diagnostic plots
  of the least squares regression fit.
  - **Answer**: There are two or more points with high leverage. There
    is heteroskedasticity in the residuals. There appears to be a
    non-linearity in the data after observing the Residuals vs Fitted
    plot. There are multiple outliers in the dataset.

<img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-9-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-9-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-9-3.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-9-4.png" width="70%" style="display: block; margin: auto;" />

    There appears to be a non-linearity in the data shown from the following plot:
    Residuals vs Fitted.

    There is heteroskedasticity in the residuals shown by the Residuals vs. Fitted
    plot. The non-constant Variance is also visible be the Q-Q Reisdual plot where
    points 331, 328, & 321 do not have constant variance.

<img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-10-1.png" width="70%" style="display: block; margin: auto;" />

**Detecting outliers**:

``` r
# Detecting Outliers
lm.fit$model <- lm.fit$model %>% mutate(row_n = row_number()) 
outliers <- subset(lm.fit$model, rstudent(lm.fit) > 3 | rstudent(lm.fit) < -3)
```

    There are 2 outliers. They are observations 321 and 328.

**Identifying the high-leverage point**:

``` r
# Identifying high-leverage point
p <- ncol(lm.fit$model)
n <- nrow(lm.fit$model)

# High-Leverage: value > 3 * (p number of parameters) / (n number of observations)
high_leverage_cutoff <- (3*p/n)

# Identifying high-leverage values
lm.hatvalues <- hatvalues(lm.fit)
high_leverage_values <- lm.hatvalues[lm.hatvalues > high_leverage_cutoff]
```

    The cutoff value for high-leverage is 0.023 given 3 predictors and 392
    observations.

    There are 8 values with high-leverage with respect to the cutoff value of 0.023.
    Observations 14, 9, and 116 are displayed as high-leverage on the following
    plot: Residuals Vs. Leverage. Their values are as follows:

             7          8          9         14         26         94         95 
    0.02559171 0.02364053 0.02762920 0.02762920 0.02364053 0.02364053 0.02762920 
           116 
    0.02975300 

**Model Summary Statistics After Removing the High-Leverage
Observation**:


    Call:
    lm(formula = auto_no_high_leverage$mpg ~ auto_no_high_leverage$horsepower)

    Residuals:
         Min       1Q   Median       3Q      Max 
    -13.6282  -3.2206  -0.2221   2.6869  16.8475 

    Coefficients:
                                      Estimate Std. Error t value Pr(>|t|)    
    (Intercept)                      40.191925   0.719252   55.88   <2e-16 ***
    auto_no_high_leverage$horsepower -0.160607   0.006488  -24.75   <2e-16 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 4.871 on 389 degrees of freedom
    Multiple R-squared:  0.6117,    Adjusted R-squared:  0.6107 
    F-statistic: 612.7 on 1 and 389 DF,  p-value: < 2.2e-16

    The R-squared value increased from 0.6059 to 0.6117 after removing the high
    leverage value! This indicates a model that captures more of the variability in
    the data.

### Question 9:

This question involves the use of multiple linear regression on the Auto
data set.

- **Question 9-a**: Produce a scatterplot matrix which includes all of
  the variables of the data set.
  - **Answer**:

Variables in Auto

    [1] "mpg"          "cylinders"    "displacement" "horsepower"   "weight"      
    [6] "acceleration" "year"         "origin"       "name"        

<img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-19-1.png" width="70%" style="display: block; margin: auto;" />

- **Question 9-b**: Compute the matrix of correlations between the
  variables using the function cor(). You will need to exclude the name
  variable, which is qualitative.
  - **Answer**:

<!-- -->

                        mpg  cylinders displacement horsepower     weight
    mpg           1.0000000 -0.7776175   -0.8051269 -0.7784268 -0.8322442
    cylinders    -0.7776175  1.0000000    0.9508233  0.8429834  0.8975273
    displacement -0.8051269  0.9508233    1.0000000  0.8972570  0.9329944
    horsepower   -0.7784268  0.8429834    0.8972570  1.0000000  0.8645377
    weight       -0.8322442  0.8975273    0.9329944  0.8645377  1.0000000
    acceleration  0.4233285 -0.5046834   -0.5438005 -0.6891955 -0.4168392
    year          0.5805410 -0.3456474   -0.3698552 -0.4163615 -0.3091199
    origin        0.5652088 -0.5689316   -0.6145351 -0.4551715 -0.5850054
                 acceleration       year     origin
    mpg             0.4233285  0.5805410  0.5652088
    cylinders      -0.5046834 -0.3456474 -0.5689316
    displacement   -0.5438005 -0.3698552 -0.6145351
    horsepower     -0.6891955 -0.4163615 -0.4551715
    weight         -0.4168392 -0.3091199 -0.5850054
    acceleration    1.0000000  0.2903161  0.2127458
    year            0.2903161  1.0000000  0.1815277
    origin          0.2127458  0.1815277  1.0000000

- **Question 9-c**: Use the lm() function to perform a multiple linear
  regression with mpg as the response and all other variables except
  name as the predictors. Use the summary() function to print the
  results. Comment on the output.

1.  Is there a relationship between the predictors and the response?
2.  Which predictors appear to have a statistically significant
    relationship to the response?
3.  What does the coefficient for the year variable suggest?

- **Answer**:

<!-- -->


    Call:
    lm(formula = mpg ~ ., data = auto_no_name_col)

    Residuals:
        Min      1Q  Median      3Q     Max 
    -9.5903 -2.1565 -0.1169  1.8690 13.0604 

    Coefficients:
                   Estimate Std. Error t value Pr(>|t|)    
    (Intercept)  -17.218435   4.644294  -3.707  0.00024 ***
    cylinders     -0.493376   0.323282  -1.526  0.12780    
    displacement   0.019896   0.007515   2.647  0.00844 ** 
    horsepower    -0.016951   0.013787  -1.230  0.21963    
    weight        -0.006474   0.000652  -9.929  < 2e-16 ***
    acceleration   0.080576   0.098845   0.815  0.41548    
    year           0.750773   0.050973  14.729  < 2e-16 ***
    origin         1.426141   0.278136   5.127 4.67e-07 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 3.328 on 384 degrees of freedom
    Multiple R-squared:  0.8215,    Adjusted R-squared:  0.8182 
    F-statistic: 252.4 on 7 and 384 DF,  p-value: < 2.2e-16

    There is a relationship between the predictors and the response as indicated by
    the F-statistic of 252.4.

    Displacement, Weight, Year, and Origin all appear to have a statistically
    significant relationship to the response.

    The coefficient of the year variable suggests that for every year, miles per
    gallon increases by 0.750773.

- **Question 9-d**: Use the plot() function to produce diagnostic plots
  of the linear regression fit. Comment on any problems you see with the
  fit. Do the residual plots suggest any unusually large outliers? Does
  the leverage plot identify any observations with unusually high
  leverage?
  - **Answer**:

<img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-25-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-25-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-25-3.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-25-4.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-25-5.png" width="70%" style="display: block; margin: auto;" />

    There are two outliers in this data as observed in the following plot:
    Studentized Residuals Vs. Fitted Values. There is heteroskedasticity as seen
    in the Residuals vs Fitted plot and the Q-Q plot. There is a high-leverage
    observation observable in the plot Residuals vs Leverage. There is a
    non-linearity observable in the Residuals vs Fitted plot.

- **Question 9-e**: User the \* and : symbols to fit linear models with
  interaction effects. Do any interactions appear to be statistically
  significant?
  - **Answer**:

<!-- -->

    The following interactions have significant relationships with respect to mpg:
    year and weight, horsepower and cylinders, and horsepower and displacement.


    Call:
    lm(formula = mpg ~ horsepower * displacement, data = auto)

    Residuals:
         Min       1Q   Median       3Q      Max 
    -10.9391  -2.3373  -0.5816   2.1698  17.5771 

    Coefficients:
                              Estimate Std. Error t value Pr(>|t|)    
    (Intercept)              5.305e+01  1.526e+00   34.77   <2e-16 ***
    horsepower              -2.343e-01  1.959e-02  -11.96   <2e-16 ***
    displacement            -9.805e-02  6.682e-03  -14.67   <2e-16 ***
    horsepower:displacement  5.828e-04  5.193e-05   11.22   <2e-16 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 3.944 on 388 degrees of freedom
    Multiple R-squared:  0.7466,    Adjusted R-squared:  0.7446 
    F-statistic:   381 on 3 and 388 DF,  p-value: < 2.2e-16


    Call:
    lm(formula = mpg ~ weight * year, data = auto)

    Residuals:
        Min      1Q  Median      3Q     Max 
    -8.0397 -1.9956 -0.0983  1.6525 12.9896 

    Coefficients:
                  Estimate Std. Error t value Pr(>|t|)    
    (Intercept) -1.105e+02  1.295e+01  -8.531 3.30e-16 ***
    weight       2.755e-02  4.413e-03   6.242 1.14e-09 ***
    year         2.040e+00  1.718e-01  11.876  < 2e-16 ***
    weight:year -4.579e-04  5.907e-05  -7.752 8.02e-14 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 3.193 on 388 degrees of freedom
    Multiple R-squared:  0.8339,    Adjusted R-squared:  0.8326 
    F-statistic: 649.3 on 3 and 388 DF,  p-value: < 2.2e-16


    Call:
    lm(formula = mpg ~ cylinders * horsepower, data = auto)

    Residuals:
         Min       1Q   Median       3Q      Max 
    -11.5862  -2.1945  -0.5617   1.9541  16.3329 

    Coefficients:
                          Estimate Std. Error t value Pr(>|t|)    
    (Intercept)          72.815097   3.071314  23.708   <2e-16 ***
    cylinders            -6.492462   0.510560 -12.716   <2e-16 ***
    horsepower           -0.416007   0.034521 -12.051   <2e-16 ***
    cylinders:horsepower  0.047247   0.004732   9.984   <2e-16 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 4.094 on 388 degrees of freedom
    Multiple R-squared:  0.727, Adjusted R-squared:  0.7249 
    F-statistic: 344.4 on 3 and 388 DF,  p-value: < 2.2e-16

- **Question 9-f**: Try a few different combinations of the variables
  such as log(X), √(X), X<sup>2</sup>. Comment on your findings.
  - **Answer**:

<!-- -->

    Three transformations were performed on weight: the log, square root, and the
    square of weight. These transformations yielded R-squared values that were
    highest with the log transformation of the weight. The log transformation model
    furthmore exhibited improved values with respect to F-statistics and Residual
    Standard Error. The transformed weight is a significant indicator of mpg in all
    three transformed linear models.


    Call:
    lm(formula = mpg ~ log(weight), data = auto)

    Residuals:
         Min       1Q   Median       3Q      Max 
    -12.4315  -2.6752  -0.2888   1.9429  16.0136 

    Coefficients:
                Estimate Std. Error t value Pr(>|t|)    
    (Intercept) 209.9433     6.0002   34.99   <2e-16 ***
    log(weight) -23.4317     0.7534  -31.10   <2e-16 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 4.189 on 390 degrees of freedom
    Multiple R-squared:  0.7127,    Adjusted R-squared:  0.7119 
    F-statistic: 967.3 on 1 and 390 DF,  p-value: < 2.2e-16


    Call:
    lm(formula = mpg ~ sqrt(weight), data = auto)

    Residuals:
         Min       1Q   Median       3Q      Max 
    -12.2402  -2.9005  -0.3708   2.0791  16.2296 

    Coefficients:
                 Estimate Std. Error t value Pr(>|t|)    
    (Intercept)  69.67218    1.52649   45.64   <2e-16 ***
    sqrt(weight) -0.85560    0.02797  -30.59   <2e-16 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 4.239 on 390 degrees of freedom
    Multiple R-squared:  0.7058,    Adjusted R-squared:  0.705 
    F-statistic: 935.4 on 1 and 390 DF,  p-value: < 2.2e-16


    Call:
    lm(formula = mpg ~ I(weight^2), data = auto)

    Residuals:
         Min       1Q   Median       3Q      Max 
    -11.2813  -3.1744  -0.4708   2.2708  17.2506 

    Coefficients:
                  Estimate Std. Error t value Pr(>|t|)    
    (Intercept)  3.447e+01  4.708e-01   73.22   <2e-16 ***
    I(weight^2) -1.150e-06  4.266e-08  -26.96   <2e-16 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 4.619 on 390 degrees of freedom
    Multiple R-squared:  0.6507,    Adjusted R-squared:  0.6498 
    F-statistic: 726.6 on 1 and 390 DF,  p-value: < 2.2e-16

### Question 10:

This question should be answered using the Carseats data set.

- **Question 10-a**: Fit a multiple regression model to fit Sales using
  Price, Urban, and US.
  - **Answer**:

<!-- -->


    Call:
    lm(formula = Sales ~ Price + Urban + US, data = Carseats)

    Coefficients:
    (Intercept)        Price     UrbanYes        USYes  
       13.04347     -0.05446     -0.02192      1.20057  

- **Question 10-b**: Provide an interpretation of each coefficient in
  the model. Be careful - some of the variables in the model are
  qualitative!
  - **Answer**:

``` r
f_print(sprintf("Every 1 unit of increase in price will decrease sales by 54.46 units. Stocking carseats in an Urban location decreases sales by 21.92 units. Stocking carseats in US stores increase sales by 1200 units."))
```

    Every 1 unit of increase in price will decrease sales by 54.46 units. Stocking
    carseats in an Urban location decreases sales by 21.92 units. Stocking carseats
    in US stores increase sales by 1200 units.

- **Question 10-c**: Write out the model in equation form, being careful
  to handle the qualitative variables properly.
  - **Answer**:

``` r
# If the Carseat is stocked in an Urban And US store:
# Sales ≈ β_0 + β_1 * Price + β_2 + β_3

# If the Carseat is stocked in an Urban store only:
# Sales ≈ β_0 + β_1 * Price + β_2

# If the Carseat is stocked in a US store only:
# Sales ≈ β_0 + β_1 * Price + β_3
```

- **Question 10-d**: For which of the predictors can you reject the null
  hypothesis H<sub>0</sub> : β<sub>j</sub> = 0?
  - **Answer**:

<!-- -->

    The following are significant predictors of sales: Price & US.


    Call:
    lm(formula = Sales ~ Price + Urban + US, data = Carseats)

    Residuals:
        Min      1Q  Median      3Q     Max 
    -6.9206 -1.6220 -0.0564  1.5786  7.0581 

    Coefficients:
                 Estimate Std. Error t value Pr(>|t|)    
    (Intercept) 13.043469   0.651012  20.036  < 2e-16 ***
    Price       -0.054459   0.005242 -10.389  < 2e-16 ***
    UrbanYes    -0.021916   0.271650  -0.081    0.936    
    USYes        1.200573   0.259042   4.635 4.86e-06 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 2.472 on 396 degrees of freedom
    Multiple R-squared:  0.2393,    Adjusted R-squared:  0.2335 
    F-statistic: 41.52 on 3 and 396 DF,  p-value: < 2.2e-16

- **Question 10-e**: On the basis of your response to the previous
  question, fit a smaller model that only uses the predictors for which
  there is evidence of association with the outcome.
  - **Answer**:

<!-- -->


    Call:
    lm(formula = Sales ~ Price + US)

    Coefficients:
    (Intercept)        Price        USYes  
       13.03079     -0.05448      1.19964  

- **Question 10-f**: How well do the models fit the data?
  - **Answer**:

<!-- -->

    The model composed of US, Urban, & Price captures 23.9275% of the variablility
    of the data with 32.98 percent error with respect to the response, sales.

    The model exclusively composed of US & Price captures 23.9263% of the
    variablility of the data with 32.94 percent error with respect to the response,
    sales.

    The US & Price model captures less variability in the data but accomodates this
    with less response error.

- **Question 10-g**: Using the model from (e), obtain 95 % confidence
  intervals for the coefficient(s).
  - **Answer**:

<!-- -->

                      2.5 %      97.5 %
    (Intercept) 11.79032020 14.27126531
    Price       -0.06475984 -0.04419543
    USYes        0.69151957  1.70776632

- **Question 10-h**: Is there evidence of outliers or high leverage
  observations in the model from (e)?
  - **Answer**:

Observations with High Leverage

        Sales Price  US
    43  10.43    24  No
    126  9.34    49  No
    166  0.37   191 Yes
    175  0.00   185  No
    314  9.33    54  No
    368 14.37    53  No

Detecting Outliers

    [1] Sales Price US   
    <0 rows> (or 0-length row.names)

    There is evidence of 6 observations with high leverage given a cutoff value
    of 0.022. This is observable in the plot Residuals vs Leverage. There are no
    outliers.

<img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-51-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-51-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-51-3.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-51-4.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-51-5.png" width="70%" style="display: block; margin: auto;" />
\### Question 11: In this problem, we will investigate the t-statistic
for the null hypothesis H<sub>0</sub>: β = 0 in simple linear regression
without an intercept. To begin, we generate a predictor x and a response
y as follows.

``` r
set.seed(1)
x <- rnorm(100)
y <- 2*x + rnorm(100)
```

- **Question 11-a**: Perform a simple linear regression of y onto x,
  without an in- tercept. Report the coefficient estimate ˆβ, the
  standard error of this coefficient estimate, and the t-statistic and
  p-value associ- ated with the null hypothesis H0 : β = 0. Comment on
  these results. (You can perform regression without an intercept using
  the command lm(y∼x+0).)

  - **Answer**:

<!-- -->

      Estimate Std. Error  t value     Pr(>|t|)
    x 1.993876  0.1064767 18.72593 2.642197e-34

``` r
f_print(sprintf("The estimate indicates that for every unit value in x, y changes by 1.993876. The standard error indicates the size of the standard deviation of the error of the estimate of y regressed onto x. In this case, its value is 0.1064767. The t value is a measure of the number of standard deviations the x coefficient is away from 0. The p-value indicates x is a significant predictor of y. The p-value is the probability of observing any number equal to the absolute value of t or larger assuming y is not regressed onto x."))
```

    The estimate indicates that for every unit value in x, y changes by 1.993876.
    The standard error indicates the size of the standard deviation of the error
    of the estimate of y regressed onto x. In this case, its value is 0.1064767.
    The t value is a measure of the number of standard deviations the x coefficient
    is away from 0. The p-value indicates x is a significant predictor of y. The
    p-value is the probability of observing any number equal to the absolute value
    of t or larger assuming y is not regressed onto x.

- **Question 11-b**: Now perform a simple linear regression of x onto y
  without an intercept, and report the coefficient estimate, its
  standard error, and the corresponding t-statistic and p-values
  associated with the null hypothesis H0 : β = 0. Comment on these
  results.
  - **Answer**:

<!-- -->

       Estimate Std. Error  t value     Pr(>|t|)
    y 0.3911145 0.02088625 18.72593 2.642197e-34

    For every 1 unit increase in 1, there is an increase of x of 0.3911145. The
    size of the standard deviation of the error of y regressed onto x is 0.02088625.
    The y coefficient is 18.72593 standard deviations away from 0. The p value
    is significant at 2.642197e-34 and indicates the probability of observing any
    number equal to the absolute value of t or larger given x is not regressed onto
    y.

- **Question 11-c**:
  - **Answer**:

$$ \beta + \beta$$

    Both regressions share the same intercept (0), t-values, and p-values. They are
    both positive in slope.


    Call:
    lm(formula = y ~ x)

    Coefficients:
    (Intercept)            x  
       -0.03769      1.99894  

<img src="Lab_3_Linear_Regression_Exercises_files/figure-gfm/unnamed-chunk-59-1.png" width="70%" style="display: block; margin: auto;" />

- **Question 11-d**: For the regression of Y onto X without an
  intercept, the t- statistic for H0 : β = 0 takes the form ˆβ/SE( ˆβ),
  where ˆβ is given by (3.38), and where

(These formulas are slightly different from those given in Sec- tions
3.1.1 and 3.1.2, since here we are performing regression without an
intercept.) Show algebraically, and confirm numeri- cally in R, that the
t-statistic can be written as

- **Answer**: What is the relationship between the results obtained in
