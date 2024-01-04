Decoding EEG During Action Observation, Motor Imagery, & Motor Execution
================
Evan Woods
2024-01-03

## Function Definitions

## Imports

# Motor Imagery & Motor Execution

## Create data structure to hold pre-processed data

## Preprocessing: Collect, Filter, Downsample, Remove Artifacts & Extract Phases

## Sliding window size of 2s

## Define Dependent and Independent Variables & MI classes

## Create Training & Test Sets & Complete Processing using FBCSP

### DataFrame of dependent and independent variables

### Fit the data to models (logistic, SVM, DeepNN)

### Validation data

### SVM


    Call:
    best.tune(METHOD = svm, train.x = y ~ ., data = train_list[[i]], 
        ranges = list(cost = c(0.001, 0.01, 0.1, 1, 10, 25, 50, 100, 
            1000)), kernel = "linear")


    Parameters:
       SVM-Type:  C-classification 
     SVM-Kernel:  linear 
           cost:  0.1 

    Number of Support Vectors:  24

### Evaluate results

    Subject 1:
         pred
    truth  0  1
        0 11  1
        1  0 10
    Accuracy: 95.455%

    Subject 2:
         pred
    truth  0  1
        0  6  2
        1  3 11
    Accuracy: 77.273%

    Subject 3:
         pred
    truth  0  1
        0 12  0
        1  3  7
    Accuracy: 86.364%

    Subject 4:
         pred
    truth  0  1
        0 11  0
        1  1 10
    Accuracy: 95.455%

    Subject 5:
         pred
    truth  0  1
        0 10  4
        1  0  8
    Accuracy: 81.818%

    Subject 6:
         pred
    truth 0 1
        0 9 3
        1 1 9
    Accuracy: 81.818%

    Subject 7:
         pred
    truth  0  1
        0 10  0
        1  2 10
    Accuracy: 90.909%

    Subject 8:
         pred
    truth  0  1
        0 11  2
        1  2  7
    Accuracy: 81.818%

    Mean Accuracy: 86.364%.
    Standard Error: ±6.872%.

    Subject 1:
         pred
    truth  0  1
        0 13  0
        1  0  9
    Accuracy: 100.000%

    Subject 2:
         pred
    truth  0  1
        0 11  0
        1  2  9
    Accuracy: 90.909%

    Subject 3:
         pred
    truth  0  1
        0 11  1
        1  2  8
    Accuracy: 86.364%

    Subject 4:
         pred
    truth  0  1
        0 13  0
        1  0  9
    Accuracy: 100.000%

    Subject 5:
         pred
    truth  0  1
        0 13  1
        1  1  7
    Accuracy: 90.909%

    Subject 6:
         pred
    truth  0  1
        0 11  3
        1  1  7
    Accuracy: 81.818%

    Subject 7:
         pred
    truth  0  1
        0 10  0
        1  0 12
    Accuracy: 100.000%

    Subject 8:
         pred
    truth  0  1
        0 14  1
        1  1  6
    Accuracy: 90.909%

    Mean Accuracy: 92.614%.
    Standard Error: ±6.845%.

    Subject 1:
         pred
    truth  0  1
        0 13  0
        1  0  9
    Accuracy: 100.000%

    Subject 2:
         pred
    truth  0  1
        0  9  0
        1  1 12
    Accuracy: 95.455%

    Subject 3:
         pred
    truth  0  1
        0 13  1
        1  0  8
    Accuracy: 95.455%

    Subject 4:
         pred
    truth  0  1
        0 11  1
        1  0 10
    Accuracy: 95.455%

    Subject 5:
         pred
    truth  0  1
        0 14  0
        1  1  7
    Accuracy: 95.455%

    Subject 6:
         pred
    truth  0  1
        0 10  1
        1  0 11
    Accuracy: 95.455%

    Subject 7:
         pred
    truth  0  1
        0 10  0
        1  0 12
    Accuracy: 100.000%

    Subject 8:
         pred
    truth  0  1
        0 11  0
        1  0 11
    Accuracy: 100.000%

    Mean Accuracy: 97.159%.
    Standard Error: ±2.352%.

    Subject 1:
         pred
    truth  0  1
        0 13  0
        1  0  9
    Accuracy: 100.000%

    Subject 2:
         pred
    truth  0  1
        0  9  0
        1  1 12
    Accuracy: 95.455%

    Subject 3:
         pred
    truth  0  1
        0 13  1
        1  0  8
    Accuracy: 95.455%

    Subject 4:
         pred
    truth  0  1
        0 11  1
        1  0 10
    Accuracy: 95.455%

    Subject 5:
         pred
    truth  0  1
        0 14  0
        1  1  7
    Accuracy: 95.455%

    Subject 6:
         pred
    truth  0  1
        0 10  1
        1  0 11
    Accuracy: 95.455%

    Subject 7:
         pred
    truth  0  1
        0 10  0
        1  0 12
    Accuracy: 100.000%

    Subject 8:
         pred
    truth  0  1
        0 11  0
        1  0 11
    Accuracy: 100.000%

    Mean Accuracy: 97.159%.
    Standard Error: ±2.352%.

## Is it possible to increase the model accuracy for a low quality model? Subject 2 & Subject 6.

    Subject 2:
         pred
    truth  0  1
        0  6  2
        1  3 11
    Accuracy: 77.273%

    Subject 8:
         pred
    truth  0  1
        0 11  2
        1  2  7
    Accuracy: 81.818%

    [1]  0.00000       NA       NA       NA       NA       NA       NA 81.81818

    Subject 2:
         pred
    truth  1
        0  8
        1 14
    Accuracy: NA%

    [1]  0 NA

    [1] 52

    [1] 52

              truth
    prediction  0  1
             0 21  3
             1  1 27

    Model Accuracy: 92.308%.

## Logistic Regression

              truth
    prediction  0  1
             0 21  3
             1  1 27

    Accuracy of Logistic Regression: 92.308%.

<img src="decoding-eeg-rhythms-during-ao-mi-me_files/figure-gfm/unnamed-chunk-36-1.png" width="70%" style="display: block; margin: auto;" />

              truth
    prediction  0  1
             0 21  2
             1  1 28

    Validation Accuracy of Logistic Regression: 94.231%.

              truth
    prediction  0  1
             0  7  3
             1  1 11

    Accuracy of Logistic Regression: 81.818%.

              fb1         fb2        fb3       fb4        fb5       fb6       fb7
    1  -3.7271281 -1.15523257 -0.9329437 -4.520687 -2.4214577 -6.333232 -6.629672
    2  -3.3536268 -0.90193832 -0.5707780 -4.533685 -2.4438329 -6.100285 -6.251423
    3  -3.1999101 -0.91534386 -0.5043843 -4.436278 -2.3197773 -5.855576 -6.152284
    4  -2.5152148 -0.68877570 -0.7510399 -4.323089 -2.7076370 -5.236428 -5.682971
    5  -1.7576912 -0.16378662 -0.1957537 -4.435499 -1.8223449 -5.844916 -5.746822
    6  -0.8384779 -2.85004581 -0.8207188 -2.039310 -0.6154169 -1.688884 -3.272080
    7  -0.5313248 -0.93049240 -0.2597092 -1.672787 -1.5563601 -2.878475 -4.467650
    8  -2.2542118 -1.10199289 -0.7514710 -4.359852 -2.0757693 -4.562201 -5.995366
    9  -3.6212234 -0.55955600 -0.8219388 -5.234576 -2.7109634 -6.235110 -6.245603
    10 -1.6237396 -0.03188006 -1.2580929 -4.321061 -1.8815604 -6.017500 -6.385375
    11 -2.7498285  0.17578146 -0.4938904 -4.839172 -1.5299201 -5.841137 -6.292290
    12 -2.5902431  0.18751616 -0.7105124 -5.074480 -1.9203590 -5.775798 -6.320992
    13 -1.4811133 -1.31662345 -0.8138603 -4.772236 -3.2341626 -5.723543 -6.228841
    14 -2.8322913 -0.92941533 -1.4483125 -4.836765 -2.2369029 -5.853941 -7.008403
    15 -2.7624723 -0.36368335 -2.5977611 -4.757884 -1.5483760 -6.058472 -5.900287
    16  0.1225306 -1.49025172 -1.0034812 -2.519961 -1.5909198 -2.862466 -2.758690
    17 -1.1298665 -1.45486434 -0.5468515 -1.733950 -1.8789005 -2.158728 -4.070269
    18 -1.2631992 -1.11717916 -1.2322044 -1.644512 -1.9134767 -2.433530 -3.937909
    19 -1.5737285 -1.73371546 -1.3418398 -4.475297 -0.9792524 -3.541624 -4.800689
    20 -1.1586194  0.50754381 -1.6898745 -4.168460 -1.7485752 -3.597172 -5.971805
    21 -1.1431067 -0.08082751 -1.2082608 -3.748731 -1.4667022 -4.026695 -5.004728
    22 -1.8435109  0.09979343 -0.7208621 -4.390538 -1.7787747 -4.483821 -5.850583
              fb8        fb9 y
    1  -2.1423806 -1.9464945 0
    2  -2.3883608 -1.9890364 0
    3  -2.3783199 -2.1195349 0
    4  -2.3589814 -2.1417791 0
    5  -2.4409734 -2.8526954 0
    6  -1.1594302 -0.8943455 0
    7  -2.0489022 -2.0400048 0
    8  -1.6953991 -1.1946704 0
    9  -1.8788751 -2.9108923 1
    10 -2.4471093 -3.1728120 1
    11 -1.7803350 -2.7568752 1
    12 -1.8894415 -2.8530796 1
    13 -2.3042992 -2.6883370 1
    14 -2.0399952 -2.3268996 1
    15 -2.3135163 -2.3302283 1
    16 -0.5425974  0.1884023 1
    17 -1.7951781 -2.0058166 1
    18 -1.7051182 -2.1302199 1
    19 -0.6343524 -1.7411947 1
    20 -1.8670650 -1.6748966 1
    21 -1.7698668 -1.4894359 1
    22 -1.4540229 -2.2448072 1

                                       
    subject_2_svm_no_high_leverage.pred  0  1
                                      0  6  3
                                      1  2 11

    [1] 92.30769

    The validation accuracy of the logistic regression model on Subject 2's data
    increased model performance from the test-set accuracy of 77.273% to 94.231%
    after removing high-leverage values detected in Subject 2's training data. After
    refitting the svm without the high leverage observations, the accuracy of the
    svm predictions driven by the test set increased by 15.035% to 92.308%.

## Deep Neural Network

### Deep NN

### Discuss Findings & Table Results (TPR, FPR, FNR, ROC curve)

# ME

Apply boosting, bagging, random forests, and BART to a data set of your
choice. Be sure to fit the models on a training set and to evaluate
their performance on a test set. How accurate are the results compared
to simple methods like linear or logistic regression? Which of these
approaches yields the best performance?
