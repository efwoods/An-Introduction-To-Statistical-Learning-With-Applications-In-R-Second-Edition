Lab 7 Non-Linear Modeling Exercises
================
Evan Woods
2023-12-22

## Applied

### Question 6:

In this exercise, you will further analyze the Wage data set considered
throughout this chapter.

- **Question 6-a**: Perform polynomial regression to predict wage using
  age. Use cross-validation to select the optimal degree *d* for the
  polynomial. What degree was chosen, and how does this compare to the
  results of hypothesis testing using ANOVA? Make a plot of the
  resulting polynomial fit to the data.
  - **Answer**:

<!-- -->

    Analysis of Variance Table

    Model  1: wage ~ poly(age, 1)
    Model  2: wage ~ poly(age, 2)
    Model  3: wage ~ poly(age, 3)
    Model  4: wage ~ poly(age, 4)
    Model  5: wage ~ poly(age, 5)
    Model  6: wage ~ poly(age, 6)
    Model  7: wage ~ poly(age, 7)
    Model  8: wage ~ poly(age, 8)
    Model  9: wage ~ poly(age, 9)
    Model 10: wage ~ poly(age, 10)
       Res.Df     RSS Df Sum of Sq        F    Pr(>F)    
    1    2998 5022216                                    
    2    2997 4793430  1    228786 143.7638 < 2.2e-16 ***
    3    2996 4777674  1     15756   9.9005  0.001669 ** 
    4    2995 4771604  1      6070   3.8143  0.050909 .  
    5    2994 4770322  1      1283   0.8059  0.369398    
    6    2993 4766389  1      3932   2.4709  0.116074    
    7    2992 4763834  1      2555   1.6057  0.205199    
    8    2991 4763707  1       127   0.0796  0.777865    
    9    2990 4756703  1      7004   4.4014  0.035994 *  
    10   2989 4756701  1         3   0.0017  0.967529    
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    The model of degree 9 was chosen as the model with the lowest test error when
    tested using cross-validation.

    The model of degree 9 is a reasonable fit to the data when examined using the
    ANOVA test.

- **Question 6-b**: Fit a step function to predict wage using age, and
  perform cross-validation to choose the optimal number of cuts. Make a
  plot of the fit obtained.
  - **Answer**:

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-16-1.png" width="70%" style="display: block; margin: auto;" />

### Question 7:

The Wage data set contains a number of other features not explored in
this chapter, such as marital status (maritl), job class (jobclass), and
others. Explore the relationships between these other predictors and
wage, and use non-linear fitting techniques in order to fit flexible
models to the data. Create plots of the results obtained, and write a
summary of your findings.

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-17-1.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-18-1.png" width="70%" style="display: block; margin: auto;" />

    [1] "1. Never Married" "2. Married"       "3. Widowed"       "4. Divorced"     
    [5] "5. Separated"    

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-21-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-21-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-21-3.png" width="70%" style="display: block; margin: auto;" />

    There is a strong relationship between marital status & Information job class
    with respect to higher wages. Those that have never been married have the lowest
    wages whereas those that have been divorced or separated are associated with
    wages that are higher than those that have never been married but lower than
    those that have been married. There is a positive trend with increasing years
    with respect to wage.

### Question 8:

Fit the non-linear models investigated in this chapter to the Auto data
set. Is there evidence for non-linear relationships in this data set?
Create informative plots to justify your answer.

      mpg cylinders displacement horsepower weight acceleration year origin
    1  18         8          307        130   3504         12.0   70      1
    2  15         8          350        165   3693         11.5   70      1
    3  18         8          318        150   3436         11.0   70      1
    4  16         8          304        150   3433         12.0   70      1
    5  17         8          302        140   3449         10.5   70      1
    6  15         8          429        198   4341         10.0   70      1
                           name
    1 chevrolet chevelle malibu
    2         buick skylark 320
    3        plymouth satellite
    4             amc rebel sst
    5               ford torino
    6          ford galaxie 500

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-3.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-4.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-5.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-6.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-7.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-8.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-9.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-10.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-11.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-12.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-13.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-14.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-15.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-16.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-17.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-18.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-19.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-20.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-21.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-22.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-23.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-24.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-25.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-26.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-27.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-28.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-29.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-30.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-31.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-32.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-33.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-34.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-35.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-36.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-37.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-38.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-39.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-40.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-41.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-28-1.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-30-1.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-31-1.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-32-1.png" width="70%" style="display: block; margin: auto;" />

### Question 9:

This question uses the variables dis (the weighted mean of distances to
five Boston employment centers) and nox (nitrogen oxides concen- tration
in parts per 10 million) from the Boston data. We will treat dis as the
predictor and nox as the response.

- **Question 9-a**: Use the poly() function to fit a cubic polynomial
  regression to predict nox using dis. Report the regression output, and
  plot the resulting data and polynomial fits.
  - **Answer**:

<!-- -->


    Call:
    lm(formula = nox ~ poly(dis, 4))

    Residuals:
         Min       1Q   Median       3Q      Max 
    -0.12295 -0.04089 -0.01073  0.02290  0.19471 

    Coefficients:
                   Estimate Std. Error t value Pr(>|t|)    
    (Intercept)    0.554695   0.002761  200.88  < 2e-16 ***
    poly(dis, 4)1 -2.003096   0.062115  -32.25  < 2e-16 ***
    poly(dis, 4)2  0.856330   0.062115   13.79  < 2e-16 ***
    poly(dis, 4)3 -0.318049   0.062115   -5.12 4.36e-07 ***
    poly(dis, 4)4  0.033547   0.062115    0.54    0.589    
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 0.06211 on 501 degrees of freedom
    Multiple R-squared:  0.7149,    Adjusted R-squared:  0.7127 
    F-statistic: 314.1 on 4 and 501 DF,  p-value: < 2.2e-16

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-34-1.png" width="70%" style="display: block; margin: auto;" />

- **Question 9-b**: Plot the polynomial fits for a range of different
  polynomial degrees (say, from 1 to 10), and report the associated
  residual sum of squares.
  - **Answer**:

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-3.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-4.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-5.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-6.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-7.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-8.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-9.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-36-10.png" width="70%" style="display: block; margin: auto;" />

- **Question 9-c**: Perform cross-validation or another approach to
  select the opti- mal degree for the polynomial, and explain your
  results.
  - **Answer**:

<!-- -->

    A training and testing validation set was used to identify the optimal value of
    the highest degree of the polynomial used to pred nox regressed onto weighted
    mean distance to 5 boston employment centers. The optimal value of the degree
    of polynomial which creates the lowest mse is 2 with a test mse value of 0.005.
    This is supported by the graph Polynomial of NOx Vs. Distance to Employment
    Centers where the highest degree of the polynomial is 2. It is observable in
    the remaining graphs that degrees above 2 have high variance and fit too closely
    to the data. And the resulting decrease in variance is not outweighed by the
    increase in bias gained from using the linear model of degree 1.

- **Question 9-d**:Use the bs() function to fit a regression spline to
  predict nox using dis. Report the output for the fit using four
  degrees of freedom. How did you choose the knots? Plot the resulting
  fit
  - **Answer**:

<!-- -->


    Call:
    lm(formula = nox ~ bs(dis, df = 4))

    Residuals:
          Min        1Q    Median        3Q       Max 
    -0.124622 -0.039259 -0.008514  0.020850  0.193891 

    Coefficients:
                     Estimate Std. Error t value Pr(>|t|)    
    (Intercept)       0.73447    0.01460  50.306  < 2e-16 ***
    bs(dis, df = 4)1 -0.05810    0.02186  -2.658  0.00812 ** 
    bs(dis, df = 4)2 -0.46356    0.02366 -19.596  < 2e-16 ***
    bs(dis, df = 4)3 -0.19979    0.04311  -4.634 4.58e-06 ***
    bs(dis, df = 4)4 -0.38881    0.04551  -8.544  < 2e-16 ***
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 0.06195 on 501 degrees of freedom
    Multiple R-squared:  0.7164,    Adjusted R-squared:  0.7142 
    F-statistic: 316.5 on 4 and 501 DF,  p-value: < 2.2e-16

    The output for the fit using four degrees of freedom is observable from the
    summary above. The knots were selected automatically using the selected 4
    degrees of freedom.

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-40-1.png" width="70%" style="display: block; margin: auto;" />

- **Question 9-e**: Now fit a regression spline for a range of degrees
  of freedom, and plot the resulting fits and report the resulting RSS.
  Describe the results obtained.
  - **Answer**:

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-41-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-41-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-41-3.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-41-4.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-41-5.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-41-6.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-41-7.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-41-8.png" width="70%" style="display: block; margin: auto;" />

- **Question 9-f**: Perform cross-validation or another approach in
  order to select the best degrees of freedom for a regression spline on
  this data. Describe your results.
  - **Answer**:

<!-- -->

    The degree of freedom that promotes the minimum mean squared error for the
    created regression spline is: 3 degrees of freedom. The calculated test mse is:
    0.0056794.

### Question 10:

This question relates to the College data set.

- **Question 10-a**: Split the data into a training set and a test set.
  Using out-of-state tuition as the response and the other variables as
  the predictors, perform forward stepwise selection on the training set
  in order to identify a satisfactory model that uses just a subset of
  the predictors.

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-47-1.png" width="70%" style="display: block; margin: auto;" />

    Subset selection object
    Call: regsubsets.formula(Outstate ~ ., data = college, subset = train, 
        method = "forward", nvmax = length(college) - 1)
    17 Variables  (and intercept)
                Forced in Forced out
    PrivateYes      FALSE      FALSE
    Apps            FALSE      FALSE
    Accept          FALSE      FALSE
    Enroll          FALSE      FALSE
    Top10perc       FALSE      FALSE
    Top25perc       FALSE      FALSE
    F.Undergrad     FALSE      FALSE
    P.Undergrad     FALSE      FALSE
    Room.Board      FALSE      FALSE
    Books           FALSE      FALSE
    Personal        FALSE      FALSE
    PhD             FALSE      FALSE
    Terminal        FALSE      FALSE
    S.F.Ratio       FALSE      FALSE
    perc.alumni     FALSE      FALSE
    Expend          FALSE      FALSE
    Grad.Rate       FALSE      FALSE
    1 subsets of each size up to 17
    Selection Algorithm: forward
              PrivateYes Apps Accept Enroll Top10perc Top25perc F.Undergrad
    1  ( 1 )  " "        " "  " "    " "    " "       " "       " "        
    2  ( 1 )  "*"        " "  " "    " "    " "       " "       " "        
    3  ( 1 )  "*"        " "  " "    " "    " "       " "       " "        
    4  ( 1 )  "*"        " "  " "    " "    " "       " "       " "        
    5  ( 1 )  "*"        " "  " "    " "    " "       " "       " "        
    6  ( 1 )  "*"        " "  " "    " "    " "       " "       " "        
    7  ( 1 )  "*"        " "  " "    " "    " "       " "       " "        
    8  ( 1 )  "*"        " "  " "    " "    " "       " "       " "        
    9  ( 1 )  "*"        " "  "*"    " "    " "       " "       " "        
    10  ( 1 ) "*"        "*"  "*"    " "    " "       " "       " "        
    11  ( 1 ) "*"        "*"  "*"    "*"    " "       " "       " "        
    12  ( 1 ) "*"        "*"  "*"    "*"    "*"       " "       " "        
    13  ( 1 ) "*"        "*"  "*"    "*"    "*"       " "       " "        
    14  ( 1 ) "*"        "*"  "*"    "*"    "*"       " "       " "        
    15  ( 1 ) "*"        "*"  "*"    "*"    "*"       " "       "*"        
    16  ( 1 ) "*"        "*"  "*"    "*"    "*"       " "       "*"        
    17  ( 1 ) "*"        "*"  "*"    "*"    "*"       "*"       "*"        
              P.Undergrad Room.Board Books Personal PhD Terminal S.F.Ratio
    1  ( 1 )  " "         " "        " "   " "      " " " "      " "      
    2  ( 1 )  " "         " "        " "   " "      " " " "      " "      
    3  ( 1 )  " "         "*"        " "   " "      " " " "      " "      
    4  ( 1 )  " "         "*"        " "   " "      " " " "      " "      
    5  ( 1 )  " "         "*"        " "   " "      "*" " "      " "      
    6  ( 1 )  " "         "*"        " "   " "      "*" " "      " "      
    7  ( 1 )  " "         "*"        " "   "*"      "*" " "      " "      
    8  ( 1 )  " "         "*"        " "   "*"      "*" "*"      " "      
    9  ( 1 )  " "         "*"        " "   "*"      "*" "*"      " "      
    10  ( 1 ) " "         "*"        " "   "*"      "*" "*"      " "      
    11  ( 1 ) " "         "*"        " "   "*"      "*" "*"      " "      
    12  ( 1 ) " "         "*"        " "   "*"      "*" "*"      " "      
    13  ( 1 ) " "         "*"        "*"   "*"      "*" "*"      " "      
    14  ( 1 ) " "         "*"        "*"   "*"      "*" "*"      "*"      
    15  ( 1 ) " "         "*"        "*"   "*"      "*" "*"      "*"      
    16  ( 1 ) "*"         "*"        "*"   "*"      "*" "*"      "*"      
    17  ( 1 ) "*"         "*"        "*"   "*"      "*" "*"      "*"      
              perc.alumni Expend Grad.Rate
    1  ( 1 )  " "         "*"    " "      
    2  ( 1 )  " "         "*"    " "      
    3  ( 1 )  " "         "*"    " "      
    4  ( 1 )  "*"         "*"    " "      
    5  ( 1 )  "*"         "*"    " "      
    6  ( 1 )  "*"         "*"    "*"      
    7  ( 1 )  "*"         "*"    "*"      
    8  ( 1 )  "*"         "*"    "*"      
    9  ( 1 )  "*"         "*"    "*"      
    10  ( 1 ) "*"         "*"    "*"      
    11  ( 1 ) "*"         "*"    "*"      
    12  ( 1 ) "*"         "*"    "*"      
    13  ( 1 ) "*"         "*"    "*"      
    14  ( 1 ) "*"         "*"    "*"      
    15  ( 1 ) "*"         "*"    "*"      
    16  ( 1 ) "*"         "*"    "*"      
    17  ( 1 ) "*"         "*"    "*"      

    The model that implements forward stepping and minimizes the means squared
    error is model 16. The test mean squared error of this model is: 4037736.564.
    This model is comprised of the following predictors: Private, Apps, Accept,
    Enroll, Top10perc, F. Undergrad, P. Undergrad, Room.Board, Books, Personal, PhD
    Terminal, S.F. Ratio, perc.alumni, Expend, & Graduation Rate.

- **Question 10-b**: Fit a GAM on the training data, using out-of-state
  tuition as the response and the features selected in the previous step
  as the predictors. Plot the results, and explain your findings.
  - **Answer**:

<!-- -->

     [1] "Private"     "Apps"        "Accept"      "Enroll"      "Top10perc"  
     [6] "Top25perc"   "F.Undergrad" "P.Undergrad" "Outstate"    "Room.Board" 
    [11] "Books"       "Personal"    "PhD"         "Terminal"    "S.F.Ratio"  
    [16] "perc.alumni" "Expend"      "Grad.Rate"  

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-3.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-4.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-5.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-6.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-7.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-8.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-9.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-10.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-11.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-12.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-13.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-14.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-15.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-51-16.png" width="70%" style="display: block; margin: auto;" />

    Not only are private universities associated with higher out-of-state tuition,
    but there is also an increase in the number of applications accepted, the
    percent of students from the top 10% of the high school graduating class,
    the cost of room and board, the percent of faculty with Ph.D.'s, the percent
    of faculty with terminal degrees, the percent of alumni who donate, the
    instructional expenditure per student, the student faculty ratio, and the
    graduation rate. However, increases in out-of-state tuition fees are also
    associated with a decrease in the number of applications, the number of new
    students enrolled, the number of fulltime undergraduates, the number of part
    time undergraduates, estimated book costs, and estimated personal spending.

- **Question 10-c**: Evaluate the model obtained on the test set, and
  explain the results obtained.
  - **Answer**:

<!-- -->

    The test mse is: 3790761.501. This value is the sum of the squares of the
    residual test observations divided by the number of observation in the test
    set. The test error is higher on the test set than for the training set. This is
    expected as the training error tends to underestimate the test error.

- **Question 10-d**: For which variables, if any, is there evidence of a
  non-linear relationship with the response?
  - **Answer**:

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-3.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-4.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-5.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-6.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-7.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-8.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-9.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-10.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-11.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-12.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-13.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-14.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-55-15.png" width="70%" style="display: block; margin: auto;" />

    It appears from the plots above that there is evidence of a non-linear
    relationship between Ph.D.'s, terminal degrees, and student faculty ratio with
    respect to out-of-state tuition.

### Question 11: In Section 7.7, it was mentioned that GAMs are generally fit using

a backfitting approach. The idea behind backfitting is actually quite
simple. We will now explore backfitting in the context of multiple
linear regression. Suppose that we would like to perform multiple linear
regression, but we do not have software to do so. Instead, we only have
software to perform simple linear regression. Therefore, we take the
following iterative approach: we repeatedly hold all but one coefficient
esti- mate fixed at its current value, and update only that coefficient
estimate using a simple linear regression. The process is continued un-
til convergence—that is, until the coefficient estimates stop changing.
View the following example:

- **Question 11-a**: Generate a response Y and two predictors
  X<sub>1</sub> and X<sub>2</sub>, with n = 100
- **Question 11-b**: Initialize βˆ1 to take on a value of your choice.
  It does not matter what value you choose.
- **Question 11-c**: Keeping ˆβ1 fixed, fit the model Y − ˆβ1X1 = β0 +
  β2X2 + ε.
- **Question 11-d**: Keeping ˆβ2 fixed, fit the model Y − ˆβ2X2 = β0 +
  β1X1 + ε.
- **Question 11-e**: Write a for loop to repeat (c) and (d) 1,000 times.
  Report the estimates of ˆβ0, ˆβ1, and ˆβ2 at each iteration of the for
  loop. Create a plot in which each of these values is displayed, with
  ˆβ0, ˆβ1, and ˆβ2 each shown in a different color.
- **Question 11-f**: Compare your answer in (e) to the results of simply
  performing multiple linear regression to predict Y using X1 and X2.
  Use the abline() function to overlay those multiple linear regression
  coefficient estimates on the plot obtained in (e).
- **Question 11-g**: On this data set, how many backfitting iterations
  were required in order to obtain a “good” approximation to the
  multiple re- gression coefficient estimates?

<!-- -->

    Iteration 1: βˆ0: 0.9917584 βˆ1: 1.8593666 βˆ2: 2.9720389

    Iteration 2: βˆ0: 1.0017565 βˆ1: 1.8562938 βˆ2: 3.0851824

    Iteration 3: βˆ0: 1.0017663 βˆ1: 1.8562908 βˆ2: 3.0852931

    Iteration 4: βˆ0: 1.0017663 βˆ1: 1.8562908 βˆ2: 3.0852932

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-59-1.png" width="70%" style="display: block; margin: auto;" />

    Coefficient Estimates β0, β1, & β2 fit to near the true value of the
    coefficients in the true value of ƒ in the first 2 iterations. This is
    observable from the value of the initial point displayed on the plot followed by
    the constant values of the estimated coefficients in the subsequent iterations.
    This is expected behavior of a model that is generated using the backfitting
    approach. The estimated coefficients generated from a mulitple linear regression
    are displayed with each backfit estimated coefficient as purple horizontal lines
    for reference.

- **Question 12**: This problem is a continuation of the previous
  exercise. In an example with p = 100, show that one can approximate
  the multiple linear regression coefficient estimates by repeatedly
  performing simple linear regression in a backfitting procedure. How
  many backfitting iterations are required in order to obtain a “good”
  approximation to the multiple regression coefficient estimates? Create
  a plot to justify your answer.
  - **Answer**: A good approximation to multiple regression coefficient
    estimates is observable after 3 iterations of the backfitting
    procedure when the number of predictors is restricted to 2 or 3.
    However, after fitting 100 predictors, the model immediately fits
    and does not subsequently change. There is significant error between
    the true value of the coefficients and the collected estimated
    coefficients. The response does apparently change, and the methods
    used are the same as when there are fewer predictors, yet the linear
    model is producing estimates that are no different even though the
    formula alters the predictors that is backfit and the same
    predictors is excluded from the dataframe. Multiple attempts have
    been made to investigate and resolve this issue including
    investigating predictors, estimated outputs, and wrangling the data.

``` r
## Example Case of 2 variables
set.seed(42)
X1 <- rnorm(100)
X2 <- rnorm(100)
ε <- rnorm(100)
β0 <- 1
β1 <- 2
β2 <- 3
Y <- β0 + β1*X1 + β2*X2 + ε

βˆ1<- 5

predictors <- matrix(data = NA, nrow = 100, ncol = 2)
true_coefficients <- c(integer(2))

predictors[, 1] <- X1
predictors[, 2] <- X2
true_intercept <- β0
true_coefficients[1] <- β1
true_coefficients[2] <- β2

βˆ0_c <- c(integer(1000))
βˆ1_c <- c(integer(1000))
βˆ2_c <- c(integer(1000))

for (i in 1:4) {
  if(i == 1) {
    a <- Y - βˆ1 * X1
    coefficient_list <- lm(a ~ predictors[, -1])$coeff  
  } else {
    a <- Y - coefficient_list[2] * X1
    coefficient_list <- lm(a ~ predictors[, -1])$coeff
    coefficient_list
  }
  
  βˆ0_c[i] <-  coefficient_list[1]
  βˆ2_c[i] <- coefficient_list[2]

  a <- Y - coefficient_list[2] * X2
  coefficient_list <- lm(a ~ predictors[, -2])$coeff
  coefficient_list
  βˆ0_c[i] <- coefficient_list[1]
  βˆ1_c[i] <- coefficient_list[2]
}
```

    After 4 iterations, it is observable that the estimated coefficients are
    unchanging for up to 7 significant digits.

    Intercept for each iteration:

    0.9917584 1.0017565 1.0017663 1.0017663

    First Coefficient for each iteration:

    1.8593666 1.8562938 1.8562908 1.8562908

    Second Coefficient for each iteration:

     2.9720389  3.0851824  3.0852931  3.0852932

    Intercept MSE:

    3.119714e-06

    First Coefficient MSE:

    0.02065235

    Second Coefficient MSE:

    0.007274926

``` r
## Example Case of 3 variables
set.seed(42)
X1 <- rnorm(100)
X2 <- rnorm(100)
X3 <- rnorm(100)
ε <- rnorm(100)
β0 <- 1
β1 <- 2
β2 <- 3
β3 <- 4
Y <- β0 + β1*X1 + β2*X2 + β3*X3 + ε

βˆ1 <- 5

predictors <- matrix(data = NA, nrow = 100, ncol = 3)
true_coefficients <- c(integer(3))

predictors[, 1] <- X1
predictors[, 2] <- X2
predictors[, 3] <- X3
true_intercept <- β0
true_coefficients[1] <- β1
true_coefficients[2] <- β2
true_coefficients[3] <- β3

βˆ0_c <- c(integer(1000))
βˆ1_c <- c(integer(1000))
βˆ2_c <- c(integer(1000))
βˆ3_c <- c(integer(1000))

for (i in seq(1:4)) {
  if (i == 1) {
    a <- Y - βˆ1 * predictors[, 1]
    coefficient_list <- lm(a ~ predictors[, -1])$coeff  
  } else {
    a <- Y - coefficient_list[2] * X1 
    coefficient_list <- lm(a ~ predictors[, -1])$coeff
  }
  βˆ0_c[i] <-  coefficient_list[1]
  βˆ2_c[i] <- coefficient_list[2]
  βˆ3_c[i] <- coefficient_list[3]

  a <- Y - coefficient_list[2] * X2
  coefficient_list <- lm(a ~ predictors[, -2])$coeff
  coefficient_list
  βˆ0_c[i] <- coefficient_list[1]
  βˆ1_c[i] <- coefficient_list[2]
  βˆ3_c[i] <- coefficient_list[3]

  a <- Y - coefficient_list[3] * X3
  coefficient_list <- lm(a ~ predictors[, -3])$coeff
  βˆ0_c[i] <- coefficient_list[1]
  βˆ1_c[i] <- coefficient_list[2]
  βˆ2_c[i] <- coefficient_list[3]  
}
```

    After 4 iterations, it is observable that the estimated coefficients are
    unchanging for up to 7 significant digits.

    Intercept for each iteration:

    1.0314861 1.0315033 1.0315033 1.0315033

    First Coefficient for each iteration:

    2.0591544 2.0577546 2.0577539 2.0577539

    Second Coefficient for each iteration:

     3.0079981  3.0088289  3.0088292  3.0088292

    Third Coefficient for each iteration:

     3.9781342  3.9683938  3.9683891  3.9683891

    Intercept MSE:

    0.0009924563

    First Coefficient MSE:

    0.003335517

    Second Coefficient MSE:

    7.795565e-05

    Third Coefficient MSE:

    0.942522

``` r
# 100 Predictors: Initialization of the true function of ƒ
set.seed(42)
true_coefficients <- seq(1:100)
ε <- rnorm(100)
intercept <-rnorm(1)

predictors <- tibble(x1 = rnorm(100))
for (i in seq(2,100)) {
  predictors[i] <- rnorm(100)
}

for ( i in seq(1, 100)) {
  if(i == 1) {
    scaled_predictors <- tibble(true_coefficients[i] * predictors[i])
  } else {
    scaled_predictors[i] <- true_coefficients[i] * predictors[i]
  }
}

sum_of_scaled_predictors <- predictors[1]
for (i in seq(2,100)) {
  sum_of_scaled_predictors <- sum_of_scaled_predictors + scaled_predictors[i]
}

Y <- intercept + sum_of_scaled_predictors + ε
collected_estimated_coefficients <- c(integer(100))
collected_intercept <- c(integer(1))
Y <- Y %>% rename('a' = 'x1')

βˆ1 <- 5

# First Pass of Collecting Estimated Coefficients
a <- Y - βˆ1 * predictors[1]
df <- tibble(a, predictors[-1])
estimated_coefficients <- lm(a ~ ., data = df)$coeff
collected_estimated_coefficients[2] <- estimated_coefficients[2]
collected_intercept <- estimated_coefficients[1]

a <- Y - estimated_coefficients[i] * predictors[i]
  df <- tibble(a, predictors[-i])
  estimated_coefficients <- lm(a ~ ., data = df)$coeff
  collected_intercept <- estimated_coefficients[1]
  collected_estimated_coefficients[i+1] <- estimated_coefficients[i+1]

for(i in seq(2, 100)){
  a <- Y - estimated_coefficients[i] * predictors[i]
  df <- tibble(a, predictors[-i])
  estimated_coefficients <- lm(a ~ ., data = df)$coeff
  collected_intercept <- estimated_coefficients[1]
  if(i == 100) {
    collected_estimated_coefficients[1] <- estimated_coefficients[2]
  } else {
    collected_estimated_coefficients[i+1] <- estimated_coefficients[i+1]
  }
} 

first_pass_collected_estimated_coefficients <- collected_estimated_coefficients
  
# 10 Iterations of the backfitting procedure
for (i in seq(1, 10)) {
    for(i in seq(1, 100)){
      if(i == 1) {
        a <- Y - collected_estimated_coefficients[1] * predictors[i]
        df <- tibble(a, predictors[-i])
        estimated_coefficients <- lm(a ~ ., data = df)$coeff
        collected_intercept <- estimated_coefficients[1]
      } else {
        a <- Y - estimated_coefficients[i] * predictors[i]
        df <- tibble(a, predictors[-i])
        estimated_coefficients <- lm(a ~ ., data = df)$coeff
        collected_intercept <- estimated_coefficients[1]  
      }
    
      if(i == 100) {
        collected_estimated_coefficients[1] <- estimated_coefficients[2]
      } else {
        collected_estimated_coefficients[i+1] <- estimated_coefficients[i+1]
      }
    }
}  
```

    Intercept & Predictors 1 - 5 after a single pass of the backfitting procedure:

    -109.344 1.895 -73.245 218.257 2.919 -219.591

    Intercept & Predictors 1 - 5 after 10 iterations of the backfitting procedure:

    -109.344 5.000 -73.245 218.257 2.919 -219.591
