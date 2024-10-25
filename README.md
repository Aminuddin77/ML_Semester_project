# Machine Failure Prediction

This project predicts machine failures using a K-Nearest Neighbors (KNN) classifier. The frontend application is built using Streamlit, providing an interactive interface for users to train the model and make predictions.

## Project Overview

Machine failures can lead to significant downtime and financial loss. This project aims to predict potential machine failures based on various parameters such as air temperature, process temperature, rotational speed, torque, tool wear, and machine type. The model can be trained on historical data, and users can input new machine parameters to predict failures.

## Deployed Application

The application is deployed and accessible at the following URL: [Machine Failure Prediction App](https://predict-machine.streamlit.app/)

## Features

- **Model Training**: Train the KNN model using historical data.
- **Predict Failure**: Input new machine parameters to predict if the machine will fail.
- **Test Data**: Test the model with a custom percentage of data to evaluate its performance.

## Usage

### Data Preprocessing

The dataset is preprocessed by:
- Dropping unnecessary columns (`UDI` and `Product ID`).
- Creating a new feature `nf` which is the product of `Tool wear [min]` and `Torque [Nm]`.
- Encoding the categorical `Type` feature using `LabelEncoder`.

### Model Training

The K-Nearest Neighbors (KNN) classifier is used for training. The optimal number of neighbors is determined by testing the accuracy of the model for `n_neighbors` ranging from 1 to 199. The best value of `n_neighbors` is selected based on the highest accuracy.

### Streamlit Frontend

The frontend application allows users to:
- Start training the model by pressing the "Start Training My Model" button.
- Input new machine parameters and predict the failure by filling out the form and pressing the "Predict Failure for New Machine" button.
- Test the model with a custom percentage of data by selecting the percentage using a slider and pressing the "Test Data on Certain Percentage" button.

## Dependencies

The following Python libraries are used in this project:
- `streamlit`
- `pandas`
- `scikit-learn`
- `time`

Make sure to install the required dependencies using the following command:
```bash
pip install -r requirements.txt
```

## Code Structure
- app.py: The main file containing the Streamlit app code.
- modelling.py: Contains the Modelling class used for training and evaluating the models.
- machine_failure_prediction.csv: The dataset used for training the model.

## How to Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/as3hr/machine-failure-prediction.git
2. Navigate to the project directory:
   ```bash
   cd machine-failure-prediction
3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
4. Run the Streamlit app:
   ```bash
   streamlit run app.py

## Conclusion

This project demonstrates how to use machine learning to predict machine failures and provides an interactive interface for users to train and test the model. The deployed application offers a user-friendly experience for predicting machine failures based on input parameters.

Feel free to contribute to this project by submitting issues or pull requests.
