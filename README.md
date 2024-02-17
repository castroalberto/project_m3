# Diamonds Prediction Project

## Machine Learning Project based on price prediction for a diamond dataset.

### Context
The project aims to create a prediction model to calculate the price of a list of diamonds, leveraging a set of features but without knowing their market price.

### My Project
To determine the price of the diamonds we have for testing, I followed the steps below:

1. Data Extraction
2. EDA (Exploratory Data Analysis)
3. Preprocessing
4. Training
5. Prediction
6. Result

These steps are explained below:

#### Data Extraction
The data is extracted from a .db file using the `duckdb` library. The extracted dataframe includes all necessary information for the model, such as price, carat, depth, table, x, y, z, city, clarity, color, and cut. The dataset comprises 40,455 rows.

#### EDA
An analysis is performed to ensure there are no null values, as the model cannot be trained with null or categorical data without preprocessing.

#### Preprocessing
The preprocessing steps include:
- Removing the "id" column from the test dataset to match the training dataset.
- Separating the training dataset into categorical and numerical columns, converting categorical data to numerical using "one hot encoding," and then concatenating these back into a single dataframe.
- To improve my model, I apply these estimated prices to my test dataset and add it to the training dataset by concatenating it.


#### SCALING
`StandardScaler` from `sklearn.preprocessing` is applied to scale the features.

#### MODELING
A `RandomForestRegressor` with 100 estimators and a random state of 42 is used as the prediction model. This model is chosen based on its performance metrics, including RMSE (Root Mean Square Error), indicating its effectiveness in predicting diamond prices accurately.
