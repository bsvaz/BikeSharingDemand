# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### BRUNO VAZ

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
It was needed to discart all negative values because this competition doesn't accept them since the target value cannot be negative. We solved this setting all negative values to zero.

### What was the top ranked model that performed?
An WeightedEnsembleModel with score on validation set of -53.11

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The exploration analysis told us what are the distributions of temperature, "feels like" temperature, humidity, windspeed and the count of rented bike. It was also plotted a graph to know what is the relationship between hour of the day and rent and it was possible to discover some patterns.
It was decided to create features for hour, day, month and year to separate them.
It was needed to transform the categorical features that was set to integer before to the correct type, so the model could interpret them in the correct way.

### How much better did your model preform after adding additional features and why do you think that is?
Much better, 74%. This occurs because setting the feature to the correct type is very important since it tells the model how to interpret them.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
The model doesn't performmed better

### If you were given more time with this dataset, where do you think you would spend more time?
I would try to train neural networks with I had time and GPUs available, since in this project we only use CPUs and we had a little time we only can train tiny neural networks.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|GBM|CAT|RF|score|
|--|--|--|--|--|
|initial|-55.2|-55.5|-53.4|1.8|
|add_features|-38.4|-38.2|-38.9|0.47|
|hpo|-39.1|-39.3|-39.7|0.49|


### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](img/model_test_score.png)

## Summary
In this project I could learn more about how to use AutoGluon and we can see that it can perform very well if we do some preprocessing to fix data types and some feature engineering, we can also see here that AutoGluon performs very well without necessity of hyperparameter tuning.