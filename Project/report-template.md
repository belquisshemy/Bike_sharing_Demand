# Report: Predict Bike Sharing Demand with AutoGluon Solution
Balqees Shemy

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
That the model with raw data performed poorly. It needed some feature engineering. Furthermore, to be able to submit my data to kaggle I needed to make sure there are no negative values.

### What was the top ranked model that performed?
WeightedEnsemble_L3 model.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
First, I split the datetime column to extra four features: year, month, day, hour; because each feature could help greatly in our final prediction of count.
Secondly, I made sure that the categorical data; season and weather are not set to int but categorical.

### How much better did your model preform after adding additional features and why do you think that is?
It performed better from score of 1.79588(raw data) to 0.69303(feature added) on test sets. This improvement is due to:
1.Adding new features helps in predicting the target value and find seasonal pattern in the model.
2.Making sure categorical data is set to dtype of category and not int makes autogluon work better with data.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Hyperparameter tuning was useful and enhanced the performance from scoring of 0.69303 to 0.48718 on test data, which is not that huge improvement.

### If you were given more time with this dataset, where do you think you would spend more time?
I will do more data analysis and spend more time in understanding the dataset. I will also spend more time in searching for hyperparameter tuning and try different parameters.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model       |hpo1       |hpo2         |hpo3        |score  |
|------------|-----------|-------------|------------|-------|
|initial     |default_val|default_val  |default_val |1.79588|
|add_features|default_val|default_val  |default_val |0.69303|
|hpo         |num_leaves:|dropout_prob:|num_round:  |0.48718|
|            |lower=26,  |0.0,         |100         |       |
|            |upper=66   |0.5          |            |       |
|------------|-----------|-------------|------------|-------|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
Concepts learnt throughout this course was applied in this project. I worked with a machine learning models to solve a regression problem using Autogluon. The final kaggle score was pretty good close to the high scores recorded on kaggle.