Decoding EEG During Action Observation, Motor Imagery, & Motor Execution
================
Evan Woods
2024-01-15

## Support Vector Classifier Results

### Motor Imagery While Sitting: Detection of Resting vs Action Observation

    Subject 1:
         pred
    truth  0  1
        0  9  3
        1  0 10
    Accuracy: 86.364%

    Subject 2:
         pred
    truth  0  1
        0  7  1
        1  4 10
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
        1  0 11
    Accuracy: 100.000%

    Subject 5:
         pred
    truth  0  1
        0 11  3
        1  0  8
    Accuracy: 86.364%

    Subject 6:
         pred
    truth 0 1
        0 9 3
        1 2 8
    Accuracy: 77.273%

    Subject 7:
         pred
    truth  0  1
        0 10  0
        1  3  9
    Accuracy: 86.364%

    Subject 8:
         pred
    truth  0  1
        0 12  1
        1  2  7
    Accuracy: 86.364%

    Mean Accuracy: 85.795%.
    Standard Error: ±7.057%.

### Motor Imagery While Sitting: Detection of Action Observation vs Motor Imagery

    Subject 1:
         pred
    truth  0  1
        0 13  0
        1  0  9
    Accuracy: 100.000%

    Subject 2:
         pred
    truth  0  1
        0 10  1
        1  2  9
    Accuracy: 86.364%

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
        1  1  8
    Accuracy: 95.455%

    Subject 5:
         pred
    truth  0  1
        0 14  0
        1  0  8
    Accuracy: 100.000%

    Subject 6:
         pred
    truth  0  1
        0 13  1
        1  0  8
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
        0 14  1
        1  0  7
    Accuracy: 95.455%

    Mean Accuracy: 94.886%.
    Standard Error: ±5.666%.

### Motor Imagery While Standing: Detection of Resting vs Action Observation

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
        0 12  0
        1  0 10
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
        0 11  0
        1  0 11
    Accuracy: 100.000%

    Subject 7:
         pred
    truth  0  1
        0 10  0
        1  2 10
    Accuracy: 90.909%

    Subject 8:
         pred
    truth  0  1
        0 11  0
        1  0 11
    Accuracy: 100.000%

    Mean Accuracy: 96.591%.
    Standard Error: ±4.029%.

### Motor Imagery While Standing: Detection of Action Observation vs Motor Imagery

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
        0 12  0
        1  0 10
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
    Standard Error: ±3.382%.

### Comparision Against Results of Prior Research

    The highest mean accuracy of the classifiers in the prior research is: 82.73%
    with a standard error of ±2.54.

    The lowest mean accuracy of the classifiers is: 85.795% with a standard error of
    7.057%.

    The highest mean accuracy of the classifiers is: 97.159% with a standard error
    of 3.382%.

    [[1]]

    Parameter tuning of 'svm':

    - sampling method: 10-fold cross validation 

    - best parameters:
     cost
        1

    - best performance: 0.02913978 

    The action observation versus motor imagery classifier during the stand to sit
    transition has the model with the highest accuracy.

    [[1]]

    Parameter tuning of 'svm':

    - sampling method: 10-fold cross validation 

    - best parameters:
     cost
       10

    - best performance: 0 

## Increasing a Subject’s Model Accuracy

    The lowest performing model of the Resting vs. Action Observation
    classifications is the model for subject #2. The accuracy of subject #2's model
    is: 77.273.

## Explore the subject with the lowest performing model’s data and find outliers, high-leverage, or non-linearities.

## Logistic Regression: Training & Validation

              truth
    prediction  0  1
             0 17  2
             1  5 28

    Validation Accuracy of Logistic Regression: 86.538%.

### Detecting Outliers

<img src="decoding-eeg-rhythms-during-ao-mi-me_files/figure-gfm/unnamed-chunk-36-1.png" width="70%" style="display: block; margin: auto;" />

    There are no detected outliers in the logistic regression fit on the subject
    with the lowest performing model's data.

### Detecting and Removing High-Leverage Values

    There are 6 high-leverage values:

           40       277       286       232        75       101 
    0.1323494 0.2253339 0.1308785 0.1635270 0.1235658 0.2007253 

### Refitting a Logistic Regression Model

              truth
    prediction  0  1
             0 19  1
             1  3 29

    Validation Accuracy of Logistic Regression with no high leverage: 92.308%.

              truth
    prediction  0  1
             0  3  3
             1  5 11

    Accuracy of Logistic Regression on the subject with the lowest performing
    model's Test Data after removing high-leverage: 63.636%. The previous accuracy
    on test data with an SVM was: 77.273%.

### Refitting the Lowest Performing Support Vector Classifier Model

              truth
    prediction  0  1
             0  5  4
             1  3 10

    [1] 68.18182

### Results

    The validation accuracy of the logistic regression model on the subject with
    the lowest performing model's data increased model performance from 86.538% to
    92.308% after removing high-leverage values detected in the subject's training
    data.

### Deep Learning Neural Network

    Epoch 1/100
    8/8 - 1s - loss: 0.2501 - accuracy: 0.5691 - val_loss: 0.2458 - val_accuracy: 0.5968 - 1s/epoch - 165ms/step
    Epoch 2/100
    8/8 - 0s - loss: 0.1863 - accuracy: 0.7358 - val_loss: 0.2268 - val_accuracy: 0.5968 - 120ms/epoch - 15ms/step
    Epoch 3/100
    8/8 - 0s - loss: 0.1828 - accuracy: 0.7276 - val_loss: 0.2070 - val_accuracy: 0.6290 - 108ms/epoch - 14ms/step
    Epoch 4/100
    8/8 - 0s - loss: 0.1724 - accuracy: 0.7602 - val_loss: 0.1844 - val_accuracy: 0.6452 - 102ms/epoch - 13ms/step
    Epoch 5/100
    8/8 - 0s - loss: 0.1590 - accuracy: 0.7724 - val_loss: 0.1732 - val_accuracy: 0.7258 - 109ms/epoch - 14ms/step
    Epoch 6/100
    8/8 - 0s - loss: 0.1448 - accuracy: 0.7886 - val_loss: 0.1646 - val_accuracy: 0.7419 - 109ms/epoch - 14ms/step
    Epoch 7/100
    8/8 - 0s - loss: 0.1467 - accuracy: 0.7764 - val_loss: 0.1591 - val_accuracy: 0.7903 - 102ms/epoch - 13ms/step
    Epoch 8/100
    8/8 - 0s - loss: 0.1384 - accuracy: 0.8049 - val_loss: 0.1436 - val_accuracy: 0.8226 - 108ms/epoch - 13ms/step
    Epoch 9/100
    8/8 - 0s - loss: 0.1418 - accuracy: 0.7846 - val_loss: 0.1389 - val_accuracy: 0.8387 - 106ms/epoch - 13ms/step
    Epoch 10/100
    8/8 - 0s - loss: 0.1398 - accuracy: 0.7967 - val_loss: 0.1310 - val_accuracy: 0.8387 - 105ms/epoch - 13ms/step
    Epoch 11/100
    8/8 - 0s - loss: 0.1199 - accuracy: 0.8455 - val_loss: 0.1264 - val_accuracy: 0.8226 - 104ms/epoch - 13ms/step
    Epoch 12/100
    8/8 - 0s - loss: 0.1294 - accuracy: 0.8211 - val_loss: 0.1224 - val_accuracy: 0.8226 - 102ms/epoch - 13ms/step
    Epoch 13/100
    8/8 - 0s - loss: 0.1325 - accuracy: 0.7927 - val_loss: 0.1192 - val_accuracy: 0.8226 - 108ms/epoch - 13ms/step
    Epoch 14/100
    8/8 - 0s - loss: 0.1169 - accuracy: 0.8496 - val_loss: 0.1171 - val_accuracy: 0.8548 - 112ms/epoch - 14ms/step
    Epoch 15/100
    8/8 - 0s - loss: 0.1286 - accuracy: 0.8049 - val_loss: 0.1127 - val_accuracy: 0.8226 - 127ms/epoch - 16ms/step
    Epoch 16/100
    8/8 - 0s - loss: 0.1335 - accuracy: 0.8171 - val_loss: 0.1112 - val_accuracy: 0.8226 - 136ms/epoch - 17ms/step
    Epoch 17/100
    8/8 - 0s - loss: 0.1197 - accuracy: 0.8293 - val_loss: 0.1092 - val_accuracy: 0.8226 - 124ms/epoch - 16ms/step
    Epoch 18/100
    8/8 - 0s - loss: 0.1152 - accuracy: 0.8293 - val_loss: 0.1068 - val_accuracy: 0.8226 - 115ms/epoch - 14ms/step
    Epoch 19/100
    8/8 - 0s - loss: 0.1181 - accuracy: 0.8211 - val_loss: 0.1069 - val_accuracy: 0.8226 - 107ms/epoch - 13ms/step

    2/2 - 0s - 112ms/epoch - 56ms/step

    1/1 - 0s - 19ms/epoch - 19ms/step

    [1] 54.54545
