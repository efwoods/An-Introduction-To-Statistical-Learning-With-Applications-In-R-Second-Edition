Lab 7 Non-Linear Modeling Exercises
================
Evan Woods
2023-12-17

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

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-15-1.png" width="70%" style="display: block; margin: auto;" />

### Question 7:

The Wage data set contains a number of other features not explored in
this chapter, such as marital status (maritl), job class (jobclass), and
others. Explore the relationships between these other predictors and
wage, and use non-linear fitting techniques in order to fit flexible
models to the data. Create plots of the results obtained, and write a
summary of your findings.

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-16-1.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-17-1.png" width="70%" style="display: block; margin: auto;" />

    [1] "1. Never Married" "2. Married"       "3. Widowed"       "4. Divorced"     
    [5] "5. Separated"    

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-20-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-20-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-20-3.png" width="70%" style="display: block; margin: auto;" />

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

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-1.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-2.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-3.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-4.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-5.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-6.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-7.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-8.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-9.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-10.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-11.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-12.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-13.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-14.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-15.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-16.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-17.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-18.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-19.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-20.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-21.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-22.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-23.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-24.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-25.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-26.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-27.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-28.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-29.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-30.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-31.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-32.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-33.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-34.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-35.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-36.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-37.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-38.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-39.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-40.png" width="70%" style="display: block; margin: auto;" /><img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-26-41.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-27-1.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-29-1.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-30-1.png" width="70%" style="display: block; margin: auto;" />

<img src="Lab_7_Non-Linear_Modeling_Exercises_files/figure-gfm/unnamed-chunk-31-1.png" width="70%" style="display: block; margin: auto;" />
