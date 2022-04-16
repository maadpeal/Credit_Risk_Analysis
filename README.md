# Credit_Risk_Analysis

## Purpose

    - The purpose is to determine which clients represent a potential risk of non-payment of a credit through the use of automatic learning algorithms, and thus make better use of the available funds.

## Results


#### RandomOverSampler
    - For this analysis we realize that the amount of low risk information is much greater than that of high risk, that is why it is used in the first instance to create a greater amount of high risk values randomly, as we can see in the image both low risk and high risk are equal in amount (image A-1).

![]()
(image A-1)

    - The balanced accuracy is 65% which means that there is a 35% chance that he will be wrong, which is quite high (image A-2).

![]()
(image A-2)

    - we can see the confusion matrix in the image (image A-3).

![]()
(image A-3)

    - The precision of the model is 55/(55+5570) = 0.009 this value is quite low, we cannot be sure if it is high risk or low.
    - The Sensitivity of the model is 55/(55+32) = 0.63 this value will also turn out to be low because it will leave out many possible high-risk credits.
    - The f1 score is 2*(0.63*0.009)/(0.63+0.009) = 0.017, this means that there is an imbalance between precision and sensitivity.

#### SMOTE
    - In this case we take another methodology to equalize the values of high risk and low risk, to create a more robust model, we use interpolation to create the new values (image B-1).

![]()
(image B-1)

    - The balanced accuracy is 65% which means that there is a 35% chance that it will be wrong, which is quite high, it is only a little below the RandomOverSampler(image B-2).

![]()
(image B-2)

    - we can see the confusion matrix in the image (image B-3).

![]()
(image B-3)

    - The precision of the model is 56/(56+5840) = 0.009 this value is quite low, we cannot be sure if it is high risk or low.
    - The Sensitivity of the model is 56/(56+31) = 0.64 this value will also turn out to be low because it will leave out many possible high-risk credits.
    - The f1 score is 2*(0.64*0.009)/(0.64+0.009) = 0.017, this means that there is an imbalance between precision and sensitivity.
    - There is no improvement that makes the difference between the present method and the previous one.

#### ClusterCentroids
    - In this case we do the opposite instead of increasing the class that has less representation, we decrease the one that has more to equalize the sample (image C-1).

![]()
(image C-1)

    - the balanced accuracy es de 52% which means that the prediction is quite random which does not help us to detect high-risk loans (image C-2).

![]()
(image C-2)

    - we can see the confusion matrix in the image (image C-3).

![]()
(image C-3)

    - The precision of the model is 53/(53+9424) = 0.005 this value is quite low, we cannot be sure if it is high risk or low.
    - The Sensitivity of the model is 53/(53+34) = 0.61 this value will also turn out to be low because it will leave out many possible high-risk credits.
    - The f1 score is 2*(0.61*0.005)/(0.61+0.005) = 0.009, this means that there is an imbalance between precision and sensitivity.
    - There is no improvement that makes the difference between the present method and the previous two, in fact it is much worse.

#### SMOTEENN
    - It is tested with the mixed solution of creating new data from the SMOTE technique and then cleaning the result to generate two better defined classes (image D-1).

![]()
(image D-1)

    - the balanced accuracy es de 63% which means that there is a 37% chance that he is wrong, which is quite high (image D-2).

![]()
(image D-2)

    - we can see the confusion matrix in the image (image D-3).

![]()
(image D-3)

    - The precision of the model is 61/(61+7294) = 0.008 this value is quite low, we cannot be sure if it is high risk or low.
    - The Sensitivity of the model is 61/(61+26) = 0.70 this value will also turn out to be low because it will leave out many possible high-risk credits.
    - The f1 score is 2*(0.70*0.008)/(0.70+0.008) = 0.015, this means that there is an imbalance between precision and sensitivity.
    - There is no improvement that makes the difference between this method and the first two, but it is better than ClusterCentroids.

#### BalancedRandomForestClassifier
    - the balanced accuracy is 67% which means that there is a 33% chance that you are wrong, which is quite high (image E-1).

![]()
(image E-1)

    - we can see the confusion matrix in the image (image E-2).

![]()
(image E-2)

    - The precision of the model is 30/(30+11) = 0.73 this value is quite acceptable because it means that it is being able to identify high-risk loans.
    - The Sensitivity of the model is 30/(30+57) = 0.34 this value is a little low because they are missing some values that are high risk.
    - The f1 score is 2*(0.34*0.73)/(0.34+0.73) = 0.46, in this case the precision and sensitivity is not as unbalanced as the previous cases.
    - There is not so much improvement that makes the difference between this method and the first two, but it is better than ClusterCentroids.

#### EasyEnsembleClassifier
    - the balanced accuracy es de 92% which means there's an 8% chance he's wrong, which is pretty good actually. (image F-1).

![]()
(image F-1)

    - we can see the confusion matrix in the image (image F-2).

![]()
(image F-2)

    - The precision of the model is 79/(79+979) = 0.07 it is a fairly low value, which means that when it predicts that a loan is high risk, we are not sure if it really is.
    - The Sensitivity of the model is 79/(79+8) = 0.91 this value is very important because it means that if you are managing to capture the majority of high-risk loans.
    - The f1 score is 2*(0.07*0.91)/(0.07+0.91) = 0.13, accuracy and sensitivity are unbalanced.
    - It is the algorithm that has presented the best results of all.


## Summary

    - As we can see from the 6 approaches we made to achieve our goal, which is to detect possible high-risk loans, most of them yielded very similar results with the exception of the last one that stood out from the others.
    - For the above reason, it is advisable to use the latter because it has better accuracy, although its precision is low, its sensitivity is very high, and this is useful for this case, because of those cases that we have found we can ask an executive to make a more exhaustive review of the cases in question and thus determine whether or not it is really a high-risk account.