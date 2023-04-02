```python

#Load the dataset into a pandas DataFrame:

import pandas as pd
import matplotlib.pyplot as plt

# Plot a histogram of each numerical feature
housing_data.hist(bins=50, figsize=(20,15))
plt.show()

# Plot a scatter matrix to see the correlation between features
from pandas.plotting import scatter_matrix

attributes = ['price', 'bedrooms', 'bathrooms', 'sqft_living', 'sqft_lot']
scatter_matrix(housing_data[attributes], figsize=(12, 8))
plt.show()
Preprocess the dataset as required:

# Check for missing values
housing_data.isnull().sum()

# Check for outliers
housing_data.describe()

# Remove outliers
housing_data = housing_data[housing_data['sqft_living'] < 8000]
housing_data = housing_data[housing_data['price'] < 6000000]

# Split the dataset into training and testing sets
from sklearn.model_selection import train_test_split

train_set, test_set = train_test_split(housing_data, test_size=0.2, random_state=42)

# Separate the target variable from the predictors
y_train = train_set['price']
X_train = train_set.drop('price', axis=1)
y_test = test_set['price']
X_test = test_set.drop('price', axis=1)

# Scale the features
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
Build a linear regression model on the training set:

from sklearn.linear_model import LinearRegression

lin_reg = LinearRegression()
lin_reg.fit(X_train_scaled, y_train)
Evaluate the performance of the model on the testing set:

from sklearn.metrics import mean_squared_error

y_pred = lin_reg.predict(X_test_scaled)
mse = mean_squared_error(y_test, y_pred)
rmse = np.sqrt(mse)
print("RMSE: ", rmse)
```
