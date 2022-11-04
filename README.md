# PI-2---Datathon---Henry

In this project I implemented machine learning to categorize price values for properties in Colombia, more precisely, to predict if a property would be expensive or cheap.

- I started by estudying the properties_colombia_train.csv data trough python pandas and dropping the columns with more NaN values (most of these with over %70 of missing data) and other columns with just descriptions that I considered not relevant for my task.

![nan_values_percentage](https://user-images.githubusercontent.com/107011436/200032353-2ed4bda7-3d30-4984-83b2-013b1e4f236f.png)

- Before I decided to drop most of the columns, I tried to fill them, mostly because those columns happened to be the ones with the state, city and neighboorhud.

![get_location_function](https://user-images.githubusercontent.com/107011436/200031892-7155854b-6f7c-414d-9ea5-16449873979f.png)

- I tried using a function with geopy to get the locations for each of these columns, but at the time of applying the function in that field it would take too long for fully filling them, it's also worth pointing that the names of the locations given by the library not all matched with the locations already in the columns, so it would have made the process of normalizing the columns all more difficult.

- With the remaining columns there were still some NaN values so I checked each individually to see if I tried to fill them or drop those entries.

- Once I have my properties_train dataframe free of missing values, I created my target label, that being if the property is considered expensive or cheap, using the mean of the column prices as the delimiter.

- For my feautures I thought the most important thing to value a property would be it's location, so since I had very few especific location data, I decided to create cardinal direction features, using as central point "El ombligo de Colombia".

- With all my features created and without missing values, I needed to encode each column to properly feed my machine learning model, so to do this I used LabelEncoder from the sklearn.preproccesing library.

- As I need to see wich features have the best correlation with my target label, I make use of the library seaborn and it's correlation heatmap.

![correlation_map](https://user-images.githubusercontent.com/107011436/200031382-5a3c9138-e1c4-4292-95fc-c787f2315bf8.png)

- Surpringsily the cardinal points that I had created didn´t had much correlation with the target label, so I decided the best was not to use them, as it would have created unnecesary noise in the prediction.

- I'll be using a Logistic Regression model to predict my target label, since I think it's more reliable when it comes to not overfit unlike a Decision Tree.

![logistic regression](https://user-images.githubusercontent.com/107011436/200031615-96979f81-d496-4fa3-8c7c-061218d8577f.png)

- Once the model is trained with my features and target label, I need it to make predictions with new data, so for that I import as a pandas dataframe the properties_colombia_test.csv file.

- And finally, I save the predictions my model did in a .csv file.

- Files used:

PI 2 Datathon, this Jupyter Notebook file cointains the estudy, transformations and implementation of the machine learning model.

properties_Colombia, .rar file containing the datasets used to train and test the model.

Auli3.csv, in this file I saved the predictions done by the model.
