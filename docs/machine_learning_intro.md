# Intro to Machine Learning

## Models

### DecisionTreeRegressor

- https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html

- https://scikit-learn.org/stable/modules/tree.html#tree

### RandomForestRegressor

- https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html

- https://scikit-learn.org/stable/modules/ensemble.html#ensembles-gradient-boosting-random-forests-bagging-voting-stacking

## Machine Learning Model

`prediction target (y)`

```
y = home_date.SalePrice
```

`predictive features (X)`

```
feature_names = ["LotArea", "YearBuilt", "1stFlrSF", "2ndFlrSF", "FullBath", "BedroomAbvGr", "TotRmsAbvGrd"]

X = home_data[feature_names]
```


`building your model`

- D e f i n e

```
melbourne_model = DecisionTreeRegressor(random_state=1)
```

- F i t

```
melbourne_model.fit(X, y)
```

- P r e d i c t

```
predictions = melbourne_model.predict(X)
```

- E v a l u a t e

```
determine how accurate the model's predictions

=> Mean Absolute Error (MAE)
```

## Model Validation

`measure the quality of your model`

- e r r o r

```
error = actual - predicted
```

- p r e d i c t

```
predicted_home_prices = melbourne_model.predict(X)
```

- m a e

```
mean_absolute_error(y, predicted_home_prices)
```

`train_test_split`

```
train_X, val_X, train_y, val_y = train_test_split(X, y, random_state = 0)

=> X (features)

    train_X, val_X

=> y (target)

    train_y, val_y
```

`define the model`

```
melbourne_model = DecisionTreeRegressor()
```

`fit the model with training data`

```
melbourne_model.fit(train_X, train_y)
```

`predict with validation data`

```
val_predictions = melbourne_model.predict(val_X)
```

`evaluate with validation data using mae`

```
mean_absolute_error(val_y, val_predictions)
```

## Underfitting and Overfitting

`underfitting`

- a model fails to capture important distinctions and patterns in the data

- performs poorly even in training data

- failing to capture relevant patterns, leading to less accurate predictions

`overfitting`

- a model matches the training data almost perfectly

- performs poorly in validation and other new data

- capturing spurious patterns that won't recur in the future, leading to less accurate predictions

`sweet spot`

- between underfitting and overfitting

- optimize the size of the tree to make better predictions

- max_leaf_nodes

## Random Forests

- the random forest uses many trees

- makes a prediction by averaging the predictions of each component tree

- generally has much better predictive accuracy than a single decision tree

- works well with default parameters