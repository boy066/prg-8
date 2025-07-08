from sklearn.linear_model import LinearRegression
import numpy as np

# Dummy data: [Size in sqft, Number of bedrooms]
X = np.array([[1000, 2], [1500, 3], [2000, 4], [1200, 2], [1800, 3]])
y = np.array([200000, 300000, 400000, 250000, 360000])  # House prices

# Initialize the Linear Regression model
model = LinearRegression()

# Train the model on the dataset
model.fit(X, y)

# Take input from the user for new house data
size = float(input("Enter the size of the house in sqft: "))
bedrooms = int(input("Enter the number of bedrooms: "))
new_data = np.array([[size, bedrooms]])

# Predict the price for the new house data
predicted_price = model.predict(new_data)

# Print the predicted price for the new house data
print("Predicted price for a house with size {} sqft and {} bedrooms: Rs.{:.2f}"
      .format(size, bedrooms, predicted_price[0]))
