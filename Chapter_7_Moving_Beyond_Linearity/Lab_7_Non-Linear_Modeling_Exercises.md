Lab 7 Non-Linear Modeling Exercises
================
Evan Woods
2023-12-20

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
    summary above. The knots where selected automatically using the selected 4
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

    THe test mse is: 3790761.501. This value is the sum of the squares of the
    residual test observations divided by the number of observation in the test
    set. The test error is higher on the test set than for the training set. This is
    expected as the training error tends to underestimate the test error.

- **Question 10-d**: For which variables, if any, is there evidence of a
  non-linear relationship with the response?
  - **Answer**:

<!-- -->

                                 Private Apps Accept Enroll Top10perc Top25perc
    Abilene Christian University     Yes 1660   1232    721        23        52
    Adelphi University               Yes 2186   1924    512        16        29
    Adrian College                   Yes 1428   1097    336        22        50
    Agnes Scott College              Yes  417    349    137        60        89
    Alaska Pacific University        Yes  193    146     55        16        44
    Albertson College                Yes  587    479    158        38        62
                                 F.Undergrad P.Undergrad Outstate Room.Board Books
    Abilene Christian University        2885         537     7440       3300   450
    Adelphi University                  2683        1227    12280       6450   750
    Adrian College                      1036          99    11250       3750   400
    Agnes Scott College                  510          63    12960       5450   450
    Alaska Pacific University            249         869     7560       4120   800
    Albertson College                    678          41    13500       3335   500
                                 Personal PhD Terminal S.F.Ratio perc.alumni Expend
    Abilene Christian University     2200  70       78      18.1          12   7041
    Adelphi University               1500  29       30      12.2          16  10527
    Adrian College                   1165  53       66      12.9          30   8735
    Agnes Scott College               875  92       97       7.7          37  19016
    Alaska Pacific University        1500  76       72      11.9           2  10922
    Albertson College                 675  67       73       9.4          11   9727
                                 Grad.Rate
    Abilene Christian University        60
    Adelphi University                  56
    Adrian College                      54
    Agnes Scott College                 59
    Alaska Pacific University           15
    Albertson College                   55

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

    Iteration 1: βˆ0: 0.995 βˆ1: 1.858 βˆ2: 3.008

    Iteration 2: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 3: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 4: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 5: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 6: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 7: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 8: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 9: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 10: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 11: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 12: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 13: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 14: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 15: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 16: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 17: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 18: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 19: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 20: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 21: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 22: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 23: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 24: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 25: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 26: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 27: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 28: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 29: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 30: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 31: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 32: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 33: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 34: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 35: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 36: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 37: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 38: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 39: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 40: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 41: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 42: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 43: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 44: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 45: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 46: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 47: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 48: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 49: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 50: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 51: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 52: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 53: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 54: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 55: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 56: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 57: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 58: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 59: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 60: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 61: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 62: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 63: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 64: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 65: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 66: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 67: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 68: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 69: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 70: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 71: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 72: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 73: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 74: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 75: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 76: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 77: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 78: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 79: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 80: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 81: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 82: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 83: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 84: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 85: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 86: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 87: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 88: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 89: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 90: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 91: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 92: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 93: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 94: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 95: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 96: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 97: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 98: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 99: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 100: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 101: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 102: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 103: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 104: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 105: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 106: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 107: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 108: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 109: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 110: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 111: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 112: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 113: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 114: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 115: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 116: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 117: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 118: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 119: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 120: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 121: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 122: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 123: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 124: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 125: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 126: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 127: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 128: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 129: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 130: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 131: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 132: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 133: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 134: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 135: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 136: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 137: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 138: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 139: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 140: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 141: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 142: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 143: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 144: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 145: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 146: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 147: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 148: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 149: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 150: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 151: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 152: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 153: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 154: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 155: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 156: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 157: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 158: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 159: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 160: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 161: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 162: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 163: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 164: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 165: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 166: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 167: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 168: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 169: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 170: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 171: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 172: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 173: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 174: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 175: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 176: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 177: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 178: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 179: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 180: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 181: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 182: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 183: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 184: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 185: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 186: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 187: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 188: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 189: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 190: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 191: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 192: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 193: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 194: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 195: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 196: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 197: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 198: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 199: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 200: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 201: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 202: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 203: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 204: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 205: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 206: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 207: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 208: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 209: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 210: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 211: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 212: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 213: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 214: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 215: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 216: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 217: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 218: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 219: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 220: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 221: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 222: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 223: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 224: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 225: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 226: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 227: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 228: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 229: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 230: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 231: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 232: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 233: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 234: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 235: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 236: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 237: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 238: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 239: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 240: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 241: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 242: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 243: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 244: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 245: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 246: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 247: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 248: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 249: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 250: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 251: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 252: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 253: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 254: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 255: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 256: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 257: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 258: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 259: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 260: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 261: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 262: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 263: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 264: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 265: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 266: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 267: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 268: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 269: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 270: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 271: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 272: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 273: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 274: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 275: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 276: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 277: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 278: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 279: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 280: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 281: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 282: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 283: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 284: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 285: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 286: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 287: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 288: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 289: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 290: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 291: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 292: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 293: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 294: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 295: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 296: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 297: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 298: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 299: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 300: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 301: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 302: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 303: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 304: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 305: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 306: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 307: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 308: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 309: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 310: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 311: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 312: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 313: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 314: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 315: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 316: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 317: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 318: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 319: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 320: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 321: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 322: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 323: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 324: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 325: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 326: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 327: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 328: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 329: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 330: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 331: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 332: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 333: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 334: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 335: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 336: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 337: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 338: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 339: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 340: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 341: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 342: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 343: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 344: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 345: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 346: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 347: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 348: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 349: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 350: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 351: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 352: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 353: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 354: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 355: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 356: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 357: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 358: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 359: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 360: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 361: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 362: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 363: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 364: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 365: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 366: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 367: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 368: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 369: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 370: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 371: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 372: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 373: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 374: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 375: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 376: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 377: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 378: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 379: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 380: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 381: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 382: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 383: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 384: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 385: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 386: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 387: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 388: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 389: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 390: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 391: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 392: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 393: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 394: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 395: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 396: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 397: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 398: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 399: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 400: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 401: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 402: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 403: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 404: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 405: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 406: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 407: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 408: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 409: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 410: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 411: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 412: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 413: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 414: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 415: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 416: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 417: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 418: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 419: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 420: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 421: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 422: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 423: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 424: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 425: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 426: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 427: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 428: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 429: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 430: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 431: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 432: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 433: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 434: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 435: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 436: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 437: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 438: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 439: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 440: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 441: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 442: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 443: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 444: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 445: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 446: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 447: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 448: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 449: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 450: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 451: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 452: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 453: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 454: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 455: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 456: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 457: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 458: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 459: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 460: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 461: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 462: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 463: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 464: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 465: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 466: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 467: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 468: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 469: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 470: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 471: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 472: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 473: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 474: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 475: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 476: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 477: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 478: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 479: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 480: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 481: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 482: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 483: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 484: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 485: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 486: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 487: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 488: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 489: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 490: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 491: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 492: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 493: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 494: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 495: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 496: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 497: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 498: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 499: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 500: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 501: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 502: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 503: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 504: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 505: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 506: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 507: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 508: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 509: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 510: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 511: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 512: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 513: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 514: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 515: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 516: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 517: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 518: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 519: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 520: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 521: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 522: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 523: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 524: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 525: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 526: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 527: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 528: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 529: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 530: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 531: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 532: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 533: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 534: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 535: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 536: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 537: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 538: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 539: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 540: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 541: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 542: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 543: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 544: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 545: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 546: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 547: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 548: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 549: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 550: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 551: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 552: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 553: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 554: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 555: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 556: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 557: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 558: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 559: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 560: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 561: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 562: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 563: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 564: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 565: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 566: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 567: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 568: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 569: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 570: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 571: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 572: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 573: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 574: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 575: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 576: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 577: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 578: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 579: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 580: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 581: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 582: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 583: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 584: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 585: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 586: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 587: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 588: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 589: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 590: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 591: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 592: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 593: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 594: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 595: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 596: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 597: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 598: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 599: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 600: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 601: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 602: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 603: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 604: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 605: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 606: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 607: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 608: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 609: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 610: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 611: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 612: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 613: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 614: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 615: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 616: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 617: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 618: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 619: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 620: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 621: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 622: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 623: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 624: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 625: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 626: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 627: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 628: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 629: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 630: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 631: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 632: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 633: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 634: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 635: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 636: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 637: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 638: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 639: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 640: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 641: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 642: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 643: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 644: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 645: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 646: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 647: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 648: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 649: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 650: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 651: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 652: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 653: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 654: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 655: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 656: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 657: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 658: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 659: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 660: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 661: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 662: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 663: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 664: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 665: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 666: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 667: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 668: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 669: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 670: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 671: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 672: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 673: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 674: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 675: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 676: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 677: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 678: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 679: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 680: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 681: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 682: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 683: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 684: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 685: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 686: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 687: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 688: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 689: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 690: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 691: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 692: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 693: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 694: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 695: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 696: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 697: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 698: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 699: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 700: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 701: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 702: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 703: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 704: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 705: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 706: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 707: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 708: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 709: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 710: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 711: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 712: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 713: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 714: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 715: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 716: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 717: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 718: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 719: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 720: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 721: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 722: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 723: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 724: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 725: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 726: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 727: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 728: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 729: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 730: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 731: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 732: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 733: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 734: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 735: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 736: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 737: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 738: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 739: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 740: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 741: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 742: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 743: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 744: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 745: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 746: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 747: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 748: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 749: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 750: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 751: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 752: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 753: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 754: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 755: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 756: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 757: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 758: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 759: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 760: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 761: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 762: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 763: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 764: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 765: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 766: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 767: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 768: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 769: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 770: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 771: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 772: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 773: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 774: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 775: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 776: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 777: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 778: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 779: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 780: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 781: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 782: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 783: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 784: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 785: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 786: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 787: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 788: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 789: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 790: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 791: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 792: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 793: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 794: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 795: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 796: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 797: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 798: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 799: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 800: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 801: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 802: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 803: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 804: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 805: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 806: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 807: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 808: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 809: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 810: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 811: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 812: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 813: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 814: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 815: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 816: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 817: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 818: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 819: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 820: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 821: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 822: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 823: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 824: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 825: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 826: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 827: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 828: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 829: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 830: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 831: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 832: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 833: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 834: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 835: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 836: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 837: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 838: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 839: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 840: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 841: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 842: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 843: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 844: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 845: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 846: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 847: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 848: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 849: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 850: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 851: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 852: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 853: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 854: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 855: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 856: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 857: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 858: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 859: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 860: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 861: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 862: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 863: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 864: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 865: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 866: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 867: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 868: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 869: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 870: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 871: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 872: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 873: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 874: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 875: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 876: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 877: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 878: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 879: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 880: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 881: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 882: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 883: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 884: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 885: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 886: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 887: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 888: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 889: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 890: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 891: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 892: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 893: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 894: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 895: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 896: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 897: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 898: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 899: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 900: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 901: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 902: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 903: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 904: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 905: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 906: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 907: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 908: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 909: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 910: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 911: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 912: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 913: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 914: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 915: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 916: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 917: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 918: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 919: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 920: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 921: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 922: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 923: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 924: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 925: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 926: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 927: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 928: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 929: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 930: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 931: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 932: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 933: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 934: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 935: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 936: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 937: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 938: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 939: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 940: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 941: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 942: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 943: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 944: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 945: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 946: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 947: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 948: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 949: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 950: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 951: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 952: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 953: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 954: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 955: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 956: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 957: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 958: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 959: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 960: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 961: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 962: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 963: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 964: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 965: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 966: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 967: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 968: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 969: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 970: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 971: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 972: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 973: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 974: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 975: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 976: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 977: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 978: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 979: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 980: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 981: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 982: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 983: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 984: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 985: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 986: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 987: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 988: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 989: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 990: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 991: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 992: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 993: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 994: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 995: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 996: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 997: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 998: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 999: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

    Iteration 1000: βˆ0: 1.002 βˆ1: 1.856 βˆ2: 3.085

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-57-1.png" width="70%" style="display: block; margin: auto;" />

    Coefficient Estimates β0, β1, & β2 fit to near the true value of the
    coefficients in the true value of ƒ in the first 2 iterations. This is
    observable from the value of the initial point displayed on the plot followed by
    the constant values of the estimated coefficients in the subsequent iterations.
    This is expected behavior of a model that is generated using the backfitting
    approach. The estimated coefficients generated from a mulitple linear regression
    are displayed with each backfit estimated coefficient as purple horizontal lines
    for reference.

    [1] 100

     [1] "coefficients"  "residuals"     "effects"       "rank"         
     [5] "fitted.values" "assign"        "qr"            "df.residual"  
     [9] "xlevels"       "call"          "terms"         "model"        

    (Intercept)          X1          X2 
       1.001766    1.856291    3.085293 
