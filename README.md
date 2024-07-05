# What Drives The Price of a Car?

![crisp_dm](/assets/crisp-dm.png)

We are tasked with following the CRISP-DM framework to determine what the key drivers are for used car prices. A csv of 426,880 records of used car data is provided for analysis. The primary objectives were broken down into the following steps:

1. Explore the data and verify quality
2. Make any necessary transformations
3. Build various models
4. Assess model performance and analyze results

The full analysis can be found [here](prompt_II_ADo.ipynb)

## 1. Explore the data and verify quality

Much of the data was missing so we drop unecessary columns and use the method `dropna()` to continue cleaning the data.

![null_values](/assets/null_values.png)

## 2. Make any necessary transformations

In order to build our models, we must convert any qualitative or non-integer values into integers or floats. Fields were adjusted using the tools OrdinalEncoder and OneHotEncoder, or by transforming strings into ints/floats as appropriate.

## 3. Build various models

We utilized a variety of models and separated these models by two sets of features to investigate.

Features 1 = ['year', 'condition', 'title_status', 'cylinders', 'odometer', 'type']
Features 2 = ['fuel', 'transmission', 'drive', 'year', 'cylinders', 'odometer']

All of our models utilized a 70/30 training/test split of the data. Shown below are the coefficient values from one of the LASSO models.

![lasso_coefs](/assets/lasso_coefs.png)

## 4. Assess model performance and analyze results¶

Though the LASSO models show strong relationships with the features `cylinders` and `odometer`. 

![scatter](/assets/scatter.png)

The data still contained some outliers and originally held many null values. The MSEs for each model were quite high between both the training and test sets which suggest we may be able to improve future models by improving our methods of selecting features or transforming the data in new ways. 

Now that we have a better understanding of the data and a handful of models, we can begin the CRISP-DM process again with these insights to further guide us.