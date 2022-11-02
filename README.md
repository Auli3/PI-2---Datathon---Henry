# PI-2---Datathon---Henry_v2

In this project I implemented machine learning to categorize price values for properties in Colombia, more precisely, to predict if a property would be expensive or cheap.

I started by estudying the .csv data trough python pandas and dropping the columns with more NaN values (most of these with over %70 of missing data) and other columns with just descriptions that I considered not relevant for my task.

With the remaining columns there were still some NaN values so I checked each individually to see if I tried to fill them or drop those entries.

Once I have my properties_train dataframe free of missing values, I created my target label, that being if the property is considered expensive or cheap, using the mean of the column prices as the delimiter.

For my feautures I used the province and city of the property, alongside the number of rooms that it has and the type of property.

With all my features created and without missing values, I needed to encode each column to properly feed my machine learning model, so to do this I used LabelEncoder from the sklearn.preproccesing library.

As I need to see wich features have the best correlation with my target label, I make use of the library seaborn and it's correlation heatmap.

I'll be using a Decision Tree Classifier model to predict my target label.

Before training the model, I searched for the best hyperparameters to use, for that I imported the RandomizedSearchCV model selection from sklearn.

Once the model is trained with my features and target label, I need it to make predictions with new data, so for that I import as a pandas dataframe another .csv file.

And finally, I save the predictions my model did in a .csv file.

Files used:

PI 2 Datathon_v2, this Jupyter Notebook file cointains the estudy, transformations and implementation of the machine learning model.

properties_Colombia.rar, .rar file containing the datasets used to train and test the model.

pred.csv, in this file I saved the predictions done by the model.
