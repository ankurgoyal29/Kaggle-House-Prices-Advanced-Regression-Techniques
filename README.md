# Kaggle-House-Prices-Advanced-Regression-Techniques

### Introduction
#### Goal:
Our goal was to predict the final price for each house using advanced regression techniques.
#### Data:
A Kaggle competition, based on property data in Ames, Iowa.
#### Evaluation:
Root-Mean-Square-Error (RMSE).

### Data Description
The data has total 79 features. We figured out that there are total 43 categorical features and 36 numerical features. And for numerical features we have 15 discrete features and 21 continuous features.


### EDA- Observations 
From our analysis we observed following things
1. SalesPrice is highly correlated with OverallQual i.e the overall rating of material and finish of the house.It is also natural that SalePrice has high positive correlation with living area and basement area.
2. More the space for GarageCars, more is the SalesPrice of the house, we have some instances of houses having too much space and less SalesPrice though.
3. We reduced multicollinearity by removing some of the features or by combining them together.

### Models Used, Comparison and Training
We trained and tested various versions of the models described with different combinations of engineered features and processed variables. We used 6 single models to individually predict the results. It is well established that a stacking/blending of the predictions by single models can improve the final results. Also it is ideal to select a few best performing but uncorrelated models for this purpose instead of considering all of them. Few best performing and least correlated models were selected and stacked together to make the final prediction. We figured out that improving the base models has significant effect on stacking model. By using blending with stacking, we were able to improve our score further.


### Results:


Model|K-Fold Score|RMSE
-----|------------|----
Linear Regression| 77%| 0.17908
Ridge Regression | 90% | 0.12821 
Lasso|90% |0.12643
Random Forest Regression|88% | 0.12821 
SVR Regression|86%|0.13021
Xgboost Regression| 91%| 0.11937 
Model Stacking| 92% |0.11401 
Model Blending|93%|0.11323


Overall our models consistently had RMSE values between 0.11323 and 0.17908. Our cross validation scores were indicative of our Kaggle scores. We took the predictions from each of our best base models (Lasso, Xgboost, SVR, Model Stacking) as the features to use for the next level. We observed out that improving the base models has significant effect on stacked model. Regressors – Lasso, SVR, RF, Ridge; Meta_Regressor - LR By further blending stacked regressor with lasso and svr, we achieved our best score of 0.11340 RMSE.

### Observations/Conclusions :
1. Since household pricing data was linear in nature, linear methods performed well.
2. We observed that the categorical features with the largest effect on housing price predictive power
are roof style, roof material, and neighbourhood.
3. Ensemble models performed really well, as they reduced the model variance by cancelling out the
variance in their constituent learners.
4. To make the data fit our models and make our models more efficiently, we use one hot encoding to
convert the categorical values to the continuous or numeric values. Specifically, we use pandas
function get dummies here.
5. We found that creating new meaningful variables held our model identify patterns that it wasn’t able
to capture using only the source data.
6. Ensemble models performed very well, as they reduced the model variance by cancelling out the
variance in their constituent learners.
7. Understanding your features can help you to improve a model
8. PCA helped reduce our feature set to small number of non-collinear features.

### Challenges:
1. Overfitting was a challenge. But can be addressed via regularization and ensemble methods.
2. Small size of dataset made some of the more complex models like Neural Networks ineffective
3. Missing data - Different features required different handling techniques, which took
experimenting and benchmarking to get right.


