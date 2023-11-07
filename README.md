Congratz to the winners !

Many thanks to kaggle team for hosting this competition,hope the winning solutions will bring useful insight to the problem.

My solution is based only on tabular data.

## Data Augmentation
The strategy has been shared in many public kernels.
You can find it here.

## Validation
I already shared my validation strategy here during the competition.

## Features
I use the following features : 'base_FVC', 'base_Percent', 'base_Age', 'Week_passed', 'Sex', 'SmokingStatus'

## FVC Prediction
Final fvc prediction is a mean of the following regressor :

- SVM
- KNN
- NN
- Quantile Regressor (0.5)
- RF
- LM
- HuberRegressor
- ElasticNet
- Lgbm

## Confidence Prediction
1 - Compute the optimal Confidence value for final fvc,which is actually:
Confidence = np.sqrt(2)*np.abs(FVC_true - FVC_pred)
2 - Use the same models in FVC prediction to train on the Confidence this time
3 - Train a binary classifier to know if Confidence<=100
4 - Use prediction from (2) and post-process them by (3)


## Things that didn't work for me
Everything with image data
Linear Augmentation on tabular data