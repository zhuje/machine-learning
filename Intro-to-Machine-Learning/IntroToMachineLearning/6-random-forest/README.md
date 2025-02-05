# Random Forests 
Shallow descision trees lead to underfitting (not enough leaves reduce mean average error). Deep descision trees lead to overfitting (model is trained to recognize patterns specific to your training data set and doesn't reflect patterns in other datasets). 

Random forrests, are a solution to underfitting and overfitting trees. It uses many trees and finds and averages the predictions from each tree. 


### Dataset split 
X = labelled attributes of the dataset 
y = target value; what we're trying to predict
training data 80% / validation data 20% = dataset 
train_X, train_y 
val_X, val_y

For example, our dataset is from zillow. We want to predict the price of a home. The 'y' would be the price of the home. The attributes that can  help us determine home price is 'X' (e.g., location, number of bedrooms, square footage of the house etc.). 

We can evaluate the accuracy of our model by looking at the mean absolute error (MAE). This number takes the difference of our prec

```
from sklearn.ensemble import RandomForestRegressor 
from sklearn.metrics import mean_absolute_error 

// instantiate the random forest 
forest_model = RandomForestRegressor(random_state=1)

// train the model
forest_model.fit(train_X, train_y)

// generate the predictions using our random forest model  
mdleb_preds = forest_model.predict(val_X)

// find the MAE 
print(mean_absolute_error(val_y, melb_preds))
```