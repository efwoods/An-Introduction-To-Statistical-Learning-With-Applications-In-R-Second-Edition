Lab 6 Linear Models and Regularization Methods Exercises
================
Evan Woods
2023-12-14

## Applied:

### Question 8:

In this exercise, we will generate simulated data, and will then use
this data to perform best subset selection.

- **Question 8-a**: Use the rnorm() function to generate a predictor X
  of length n = 100, as well as a noise vector ε of length n = 100.
  - **Answer**:

``` r
set.seed(1)
X = rnorm(100)
ε = rnorm(100)
```

- **Question 8-b**: Generate a response vector Y of length n = 100
  according to the model Y = β<sub>0</sub> + β<sub>1</sub>X +
  β<sub>2</sub>X<sup>2</sup> + β<sub>3</sub>X<sup>3</sup> + ε, where
  β<sub>0</sub>, β<sub>1</sub>, β<sub>2</sub>, and β<sub>3</sub> are
  constants of your choice.
  - **Answer**:

``` r
β_0 <- 10
β_1 <- 1
β_2 <- 2
β_3 <- 3
n = 100
Y <- β_0 + (β_1 * X) + (β_2 * X^2) + (β_3 * X^3) + ε
```

- **Question 8-c**: Use the regsubsets() function to perform best subset
  selection in order to choose the best model containing the predictors
  X, X<sup>2</sup>, …, X<sup>10</sup>. What is the best model obtained
  according to C<sub>p</sub>, BIC, and adjusted R<sup>2</sup>? Show
  plots to provide evidence for your answer, and report the coefficients
  of the best model obtained. Note you will need to use the data.frame()
  function to create a single data set containing both X and Y.
  - **Answer**:

<!-- -->

    Subset selection object
    Call: regsubsets.formula(Y ~ ., data = df, nvmax = 10)
    10 Variables  (and intercept)
           Forced in Forced out
    X          FALSE      FALSE
    `X^2`      FALSE      FALSE
    `X^3`      FALSE      FALSE
    `X^4`      FALSE      FALSE
    `X^5`      FALSE      FALSE
    `X^6`      FALSE      FALSE
    `X^7`      FALSE      FALSE
    `X^8`      FALSE      FALSE
    `X^9`      FALSE      FALSE
    `X^10`     FALSE      FALSE
    1 subsets of each size up to 10
    Selection Algorithm: exhaustive
              X   `X^2` `X^3` `X^4` `X^5` `X^6` `X^7` `X^8` `X^9` `X^10`
    1  ( 1 )  " " " "   "*"   " "   " "   " "   " "   " "   " "   " "   
    2  ( 1 )  " " "*"   "*"   " "   " "   " "   " "   " "   " "   " "   
    3  ( 1 )  "*" "*"   "*"   " "   " "   " "   " "   " "   " "   " "   
    4  ( 1 )  "*" "*"   "*"   " "   "*"   " "   " "   " "   " "   " "   
    5  ( 1 )  "*" "*"   "*"   " "   "*"   "*"   " "   " "   " "   " "   
    6  ( 1 )  "*" "*"   "*"   " "   " "   " "   "*"   "*"   "*"   " "   
    7  ( 1 )  "*" "*"   "*"   " "   "*"   "*"   " "   "*"   " "   "*"   
    8  ( 1 )  "*" "*"   "*"   "*"   " "   "*"   " "   "*"   "*"   "*"   
    9  ( 1 )  "*" "*"   "*"   "*"   "*"   "*"   " "   "*"   "*"   "*"   
    10  ( 1 ) "*" "*"   "*"   "*"   "*"   "*"   "*"   "*"   "*"   "*"   

    The best model obtained according to Mallows' Cp is model 4.

    The best model obtained according to Bayesian Information Criterion is model 3.

    The best model obtained according to Adjusted R-squared is model 4.

<img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-10-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-10-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-10-3.png" width="70%" style="display: block; margin: auto;" />

    The coefficients for the best model obtained:

    (Intercept)           X       `X^2`       `X^3`       `X^5` 
    10.07200775  1.38745596  1.84575641  2.55797426  0.08072292 

- **Question 8-d**: Repeat the previous question using forward stepwise
  selection and also using backwards stepwise selection. How does your
  answer compare to the results in the previous question?
  - **Answer**:

<!-- -->

    Subset selection object
    Call: regsubsets.formula(Y ~ ., data = df, nvmax = 10, method = "forward")
    10 Variables  (and intercept)
           Forced in Forced out
    X          FALSE      FALSE
    `X^2`      FALSE      FALSE
    `X^3`      FALSE      FALSE
    `X^4`      FALSE      FALSE
    `X^5`      FALSE      FALSE
    `X^6`      FALSE      FALSE
    `X^7`      FALSE      FALSE
    `X^8`      FALSE      FALSE
    `X^9`      FALSE      FALSE
    `X^10`     FALSE      FALSE
    1 subsets of each size up to 10
    Selection Algorithm: forward
              X   `X^2` `X^3` `X^4` `X^5` `X^6` `X^7` `X^8` `X^9` `X^10`
    1  ( 1 )  " " " "   "*"   " "   " "   " "   " "   " "   " "   " "   
    2  ( 1 )  " " "*"   "*"   " "   " "   " "   " "   " "   " "   " "   
    3  ( 1 )  "*" "*"   "*"   " "   " "   " "   " "   " "   " "   " "   
    4  ( 1 )  "*" "*"   "*"   " "   "*"   " "   " "   " "   " "   " "   
    5  ( 1 )  "*" "*"   "*"   " "   "*"   "*"   " "   " "   " "   " "   
    6  ( 1 )  "*" "*"   "*"   " "   "*"   "*"   " "   " "   "*"   " "   
    7  ( 1 )  "*" "*"   "*"   " "   "*"   "*"   "*"   " "   "*"   " "   
    8  ( 1 )  "*" "*"   "*"   " "   "*"   "*"   "*"   "*"   "*"   " "   
    9  ( 1 )  "*" "*"   "*"   " "   "*"   "*"   "*"   "*"   "*"   "*"   
    10  ( 1 ) "*" "*"   "*"   "*"   "*"   "*"   "*"   "*"   "*"   "*"   

    The best model obtained implementing forward stepwise selection according to
    Mallows' Cp is model 4.

    The best model obtained implementing forward stepwise selection according to
    Bayesian Information Criterion is model 3.

    The best model obtained implementing forward stepwise selection according to
    Adjusted R-squared is model 4.

<img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-14-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-14-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-14-3.png" width="70%" style="display: block; margin: auto;" />

    Subset selection object
    Call: regsubsets.formula(Y ~ ., data = df, nvmax = 10, method = "backward")
    10 Variables  (and intercept)
           Forced in Forced out
    X          FALSE      FALSE
    `X^2`      FALSE      FALSE
    `X^3`      FALSE      FALSE
    `X^4`      FALSE      FALSE
    `X^5`      FALSE      FALSE
    `X^6`      FALSE      FALSE
    `X^7`      FALSE      FALSE
    `X^8`      FALSE      FALSE
    `X^9`      FALSE      FALSE
    `X^10`     FALSE      FALSE
    1 subsets of each size up to 10
    Selection Algorithm: backward
              X   `X^2` `X^3` `X^4` `X^5` `X^6` `X^7` `X^8` `X^9` `X^10`
    1  ( 1 )  " " " "   "*"   " "   " "   " "   " "   " "   " "   " "   
    2  ( 1 )  " " " "   "*"   "*"   " "   " "   " "   " "   " "   " "   
    3  ( 1 )  " " " "   "*"   "*"   " "   "*"   " "   " "   " "   " "   
    4  ( 1 )  "*" " "   "*"   "*"   " "   "*"   " "   " "   " "   " "   
    5  ( 1 )  "*" " "   "*"   "*"   " "   "*"   " "   "*"   " "   " "   
    6  ( 1 )  "*" " "   "*"   "*"   " "   "*"   " "   "*"   " "   "*"   
    7  ( 1 )  "*" " "   "*"   "*"   " "   "*"   " "   "*"   "*"   "*"   
    8  ( 1 )  "*" "*"   "*"   "*"   " "   "*"   " "   "*"   "*"   "*"   
    9  ( 1 )  "*" "*"   "*"   "*"   "*"   "*"   " "   "*"   "*"   "*"   
    10  ( 1 ) "*" "*"   "*"   "*"   "*"   "*"   "*"   "*"   "*"   "*"   

    The best model obtained implementing backward stepwise selection according to
    Mallows' Cp is model 7.

    The best model obtained implementing backward stepwise selection according to
    Bayesian Information Criterion is model 5.

    The best model obtained implementing backward stepwise selection according to
    Adjusted R-squared is model 7.

<img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-16-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-16-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-16-3.png" width="70%" style="display: block; margin: auto;" />

    3 different rubrics (Mallows' Cp, Bayesian Information Criterion, and Adjusted
    R-squared) identified the same best models independent of whether those models
    were created using the forward stepwise selection method or the best subset
    selection method. Those models were models 4, 3, & 4 respectively. However, the
    same three metrics identified models 7, 5, & 7 as the best models when those
    models were created using backward stepwise selection.

- **Question 8-e**: Now fit a lasso model to the simulated data, again
  using X, X<sup>2</sup>, …, X<sup>10</sup> as predictors. Use
  cross-validation to select the optimal value of λ. Create plots of the
  cross-validation error as a function of λ. Report the resulting
  coefficient estimates, and discuss the results obtained.
  - **Answer**:
    <img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-18-1.png" width="70%" style="display: block; margin: auto;" />

<!-- -->

    The coefficient estimates of the full model fit for the best value of lambda
    that minimizes mean square error are the following:

     (Intercept)  (Intercept)            X        `X^2`        `X^3`        `X^4` 
    10.160711222  0.000000000  1.201022091  1.648813427  2.771674080  0.040774671 
           `X^5`        `X^6`        `X^7`        `X^8`        `X^9` 
     0.020058585  0.000000000  0.003855428  0.000000000  0.000000000 

- **Question 8-f**: Now generate a response vector Y according to the
  model Y = β<sub>0</sub> + β<sub>7</sub>X<sup>7</sup> + ε and perform
  best subset selection and the lasso. Discuss the results obtained.
  - **Answer**:

<!-- -->

    Subset selection object
    Call: regsubsets.formula(Y ~ ., data = df, nvmax = 10)
    10 Variables  (and intercept)
           Forced in Forced out
    X          FALSE      FALSE
    `X^2`      FALSE      FALSE
    `X^3`      FALSE      FALSE
    `X^4`      FALSE      FALSE
    `X^5`      FALSE      FALSE
    `X^6`      FALSE      FALSE
    `X^7`      FALSE      FALSE
    `X^8`      FALSE      FALSE
    `X^9`      FALSE      FALSE
    `X^10`     FALSE      FALSE
    1 subsets of each size up to 10
    Selection Algorithm: exhaustive
              X   `X^2` `X^3` `X^4` `X^5` `X^6` `X^7` `X^8` `X^9` `X^10`
    1  ( 1 )  " " " "   " "   " "   " "   " "   "*"   " "   " "   " "   
    2  ( 1 )  " " "*"   " "   " "   " "   " "   "*"   " "   " "   " "   
    3  ( 1 )  " " "*"   " "   " "   "*"   " "   "*"   " "   " "   " "   
    4  ( 1 )  "*" "*"   "*"   " "   " "   " "   "*"   " "   " "   " "   
    5  ( 1 )  "*" "*"   "*"   "*"   " "   " "   "*"   " "   " "   " "   
    6  ( 1 )  "*" " "   "*"   " "   " "   "*"   "*"   "*"   " "   "*"   
    7  ( 1 )  "*" " "   "*"   " "   "*"   "*"   "*"   "*"   " "   "*"   
    8  ( 1 )  "*" "*"   "*"   "*"   " "   "*"   "*"   "*"   " "   "*"   
    9  ( 1 )  "*" "*"   "*"   "*"   " "   "*"   "*"   "*"   "*"   "*"   
    10  ( 1 ) "*" "*"   "*"   "*"   "*"   "*"   "*"   "*"   "*"   "*"   

    The best model obtained according to Mallows' Cp is model 2.

    The best model obtained according to Bayesian Information Criterion is model 1.

    The best model obtained according to Adjusted R-squared is model 4.

<img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-19-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-19-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-19-3.png" width="70%" style="display: block; margin: auto;" />
<img src="Lab_6_Linear_Models_and_Regularization_Methods_Exercises_files/figure-gfm/unnamed-chunk-20-1.png" width="70%" style="display: block; margin: auto;" />

    The coefficient estimates of the full model fit for the best value of lambda
    that minimizes mean square error are the following:

    (Intercept) (Intercept)           X       `X^2`       `X^3`       `X^4` 
       10.92532     0.00000     0.00000     0.00000     0.00000     0.00000 
          `X^5`       `X^6`       `X^7`       `X^8`       `X^9` 
        0.00000     0.00000     6.77179     0.00000     0.00000 

    Using best subset selection to generate models, Mallows' Cp, Bayesian
    Information Criterion, & Adjusted R-squared all indicated distinct best models.
    BIC indicated that model 1, which was composed of a predictor of only X^7, was
    the best model. This was followed by Mallows' Cp which indicated X^7 paired
    with X^2 best modeled the true function of ƒ. Adjusted R-squared was the poorest
    indicator of the best model. Adjusted R-squared indicated that model 4 (composed
    of X, X^2, X^3, & X^7) was the best model. Lasso Regression, however, indicated
    the true function of ƒ where the selected coefficients of the model which is fit
    for the best value of lambda are the intercept and X^7. This indicates that in
    a real world scenario, it is best (if feasable) to fit muliple models to compare
    and contrast between the selected coefficients so as to determine the true
    function of ƒ. Had the true function of ƒ not been known, it would have been
    clear that X^7 and the intercept are related to the response in a significant
    way due to the fact that both lasso regression and another statistic, BIC in
    this case, identified these coefficients as pertinent to a model which predicts
    the desired response.

### Question 9:

In this exercise, we will predict the number of applications received
using the other variables in the College dataset. \* **Question 9-a**:
Split the data into a training set and a test set.

``` r
train <- sample(nrow(college), nrow(college)/2)
test <- (-train)
```

- **Question 9-b**: Fit a linear model using least squares on the
  training set, and report the test error obtained.
  - **Answer**:

<!-- -->

    The test error of the linear model is: 330681.9.

- **Question 9-c**: Fit a ridge regression model on the training set,
  with λ chosen by cross-validation. Report the test error obtained.
  - **Answer**:

<!-- -->

    The test error for the ridge regression model is 342942.031 for the chosen value
    of λ: 18.738.

- **Question 9-d**: Fit a lasso model on the training set, with λ chosen
  by cross-validation. Report the test error obtained, along with the
  number of non-zero coefficient estimates.
  - **Answer**:

<!-- -->

    The test error for the lasso model is 342942.031 for the chosen value of λ:
    18.738.

    The number of non-zero coefficient estimates is 8.
