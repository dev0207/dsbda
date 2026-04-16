
# Car Price Prediction

This project predicts the selling price of a used car based on details such as present price, kilometers driven, fuel type, seller type, transmission type, number of previous owners, and vehicle age.

The machine learning workflow is built in `Untitled.ipynb`, and the trained model is served through a Flask web application in `app.py`.

## Project Overview

The goal of this project is to estimate a car's resale price using supervised machine learning. The dataset is cleaned, transformed, and used to train a Random Forest Regression model. The final trained model is saved as a pickle file and loaded by the Flask app to make predictions from user input.

## Features Used

- Present price of the car
- Kilometers driven
- Fuel type
- Seller type
- Transmission type
- Number of previous owners
- Age of the car

## Dataset

The dataset used in this project is stored in:

```text
car data.csv
```

It contains information about used cars, including their selling price and related vehicle attributes. The target variable is:

```text
Selling_Price
```

## Machine Learning Workflow

The notebook follows these main steps:

1. Import required libraries.
2. Load the car dataset.
3. Explore dataset shape, missing values, and categorical values.
4. Create a final dataset with useful columns.
5. Add car age using the current year.
6. Convert categorical columns into dummy variables.
7. Analyze feature correlations.
8. Split data into training and testing sets.
9. Train a Random Forest Regressor.
10. Tune model hyperparameters using `RandomizedSearchCV`.
11. Evaluate the model using MAE, MSE, and RMSE.
12. Save the trained model using pickle.

## Model

The trained model is saved as:

```text
random_forest_regression_model.pkl
```

This model is loaded by the Flask application to generate price predictions.

## Project Structure

```text
Car-Price-Prediction/
├── Untitled.ipynb
├── app.py
├── main.py
├── car data.csv
├── random_forest_regression_model.pkl
├── requirements.txt
├── Procfile
├── README.md
└── templates/
    └── index.html
```

## Installation

Clone or download the project, then install the required dependencies.

```bash
pip install -r requirements.txt
```

## How To Run The Flask App

Run the application with:

```bash
python app.py
```

Then open the local URL shown in the terminal, usually:

```text
http://127.0.0.1:5000/
```

Enter the car details in the form to get the predicted selling price.

## Example Inputs

The app expects values such as:

- Year of purchase
- Present price
- Kilometers driven
- Fuel type: Petrol or Diesel
- Seller type: Dealer or Individual
- Transmission: Manual or Automatic
- Owner count

## Evaluation Metrics

The notebook evaluates the regression model using:

- Mean Absolute Error
- Mean Squared Error
- Root Mean Squared Error

These metrics help measure how close the predicted selling prices are to the actual selling prices.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Flask
- Pickle

## Notes

- The app currently calculates car age using the fixed year `2020`, matching the training notebook.
- The trained model file must be present in the project folder before running the Flask app.
- `app.py` and `main.py` contain the same Flask application code.
