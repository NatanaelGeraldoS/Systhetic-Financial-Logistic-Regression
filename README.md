# Fraud Detection using Logistic Regression

This project implements a Logistic Regression model to detect fraudulent transactions using the [PaySim dataset](https://www.kaggle.com/datasets/ealaxi/paysim1/data). The dataset simulates mobile money transactions and contains various features that can be used to predict whether a transaction is fraudulent.

## Project Overview

The goal of this project is to build a predictive model that can classify transactions as either fraudulent or non-fraudulent. This model is trained using a subset of features from the dataset and uses logistic regression to make predictions.

## Dataset

The dataset used in this project is the PaySim dataset, which includes the following key features:

- `amount`: The amount of money being transferred.
- `isPayment`: A feature indicating whether the transaction is a payment (1 for payment, 0 otherwise).
- `isMovement`: A feature indicating whether the transaction is a movement of money (e.g., cash out or transfer).
- `accountDiff`: The absolute difference between the original and destination account balances.
- `isFraud`: The label indicating whether the transaction is fraudulent (1 for fraud, 0 otherwise).

## Installation

To run this project, you need to have Python installed along with the following packages:

```bash
pip install pandas numpy scikit-learn matplotlib
```

## Usage

1. **Load the dataset**: The dataset is loaded from a CSV file named `transactions.csv`.

2. **Preprocess the data**: Features are selected and scaled using `StandardScaler` from `scikit-learn`.

3. **Split the data**: The data is split into training and testing sets.

4. **Train the model**: The Logistic Regression model is trained on the training data.

5. **Evaluate the model**: The model's accuracy and coefficients are evaluated.

6. **Make predictions**: The model can predict the likelihood of transactions being fraudulent on new transaction data.

### Example

Below is an example of how to run the model and make predictions:

```python
# Initialize the model
model = LogisticRegression()
model.fit(features_train, label_train)

# Score of the training result
print("Training accuracy:", model.score(features_train, label_train))

# Make predictions on new transaction data
new_transactions = np.array([[6472.54, 1.0, 0.0, 55901.23]])
scaled_transactions = scaler.transform(new_transactions)
predictions = model.predict(scaled_transactions)
probabilities = model.predict_proba(scaled_transactions)

print("Predicted label:", predictions)
print("Probability of being fraudulent:", probabilities)
```

## Results

- The trained Logistic Regression model provides a baseline accuracy on the training data.
- Coefficients from the model give insight into which features are most influential in predicting fraud.
