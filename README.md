# Covid India Daily Cases

Continuing to the previous observations, we know take following attributes into account and train model for daily cases instead of active cases.

check the discussion: https://github.com/navalctm/CovidIndiaActiveCases

Date -> Date reformatted to Weka
Daily Deaths -> Daily number of deaths
Daily -> Daily number of cases 

As evident from the previous discussions, we will go for KNN in weka which is Instance Based Classifier (IBk) under name Lazy.

**1. KNN (IBk) regression**

K = 1 (cross validation 10 fold)
```
Correlation coefficient                  0.9112
Mean absolute error                  15700.5414
Root mean squared error              35057.1685
Relative absolute error                 31.061  %
Root relative squared error             41.5447 %
Total Number of Instances              474  
```

K = 2 (cross validation 10 fold)
```
Correlation coefficient                  0.9239
Mean absolute error                  15722.6261
Root mean squared error              32295.904 
Relative absolute error                 31.1047 %
Root relative squared error             38.2724 %
Total Number of Instances              474   
```

K = 10 (cross validation 10 fold)

```
Correlation coefficient                  0.9511
Mean absolute error                  12606.8041
Root mean squared error              26023.4953
Relative absolute error                 24.9406 %
Root relative squared error             30.8393 %
Total Number of Instances              474 
```

K = 11 (cross validation 10 fold)
```
Correlation coefficient                  0.9499
Mean absolute error                  12588.898 
Root mean squared error              26360.6848
Relative absolute error                 24.9052 %
Root relative squared error             31.2389 %
Total Number of Instances              474 
```

As we could see the error doesn't reduce significantly and after K = 10 it even increases further. 

For this case we will Use training set. 
**Note: It is a point of discussion why cross-validation set gives out that much error**

_K = 1 (training set)_
```
Correlation coefficient                  0.9982
Mean absolute error                   1483.1328
Root mean squared error               5087.7474
Relative absolute error                  2.942  %
Root relative squared error              6.042  %
Total Number of Instances              474  
```

<img src="https://github.com/navalctm/CovidIndiaDailyCases/blob/main/Images/knn_k1.png" alt="alt text" width="900" height="400">

_K = 2 (training set)_
```
Correlation coefficient                  0.9982
Mean absolute error                   1483.1328
Root mean squared error               5087.7474
Relative absolute error                  2.942  %
Root relative squared error              6.042  %
Total Number of Instances              474
```

<img src="https://github.com/navalctm/CovidIndiaDailyCases/blob/main/Images/knn_k2.png" alt="alt text" width="900" height="400">

_K = 3 (training set)_
```
Correlation coefficient                  0.9699
Mean absolute error                  10086.6883
Root mean squared error              20526.3203
Relative absolute error                 20.0084 %
Root relative squared error             24.3761 %
Total Number of Instances              474
```

<img src="https://github.com/navalctm/CovidIndiaDailyCases/blob/main/Images/knn_k3.png" alt="alt text" width="900" height="400">


**2. Using test set to predict** 


<img src="https://github.com/navalctm/CovidIndiaDailyCases/blob/main/Images/test.png" alt="alt text" width="900" height="400">

_It is evident from this data that predicting daily is achieved with model trained on this particular kind of data_

Also as a matter of fact the predicted daily remains higher, it is because of the number of deaths, this also indicates that the reported number of covid cases are actually less but in actual they could be more.


