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
1.SalesPrice is highly correlated with OverallQual i.e the overall rating of material and finish of the house.It is also natural that SalePrice has high positive correlation with living area and basement area.
2.More the space for GarageCars, more is the SalesPrice of the house, we have some instances of houses having too much space and less SalesPrice though.
3.We reduced multicollinearity by removing some of the features or by combining them together.


