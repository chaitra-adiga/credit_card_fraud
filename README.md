# CreditCardFraudDetection

A Webapp made in Django which implements a model which detects whether the given transaction is Fraudulent or Not.

## Overview

This project is a Django-based web application designed to detect fraudulent credit card transactions. It takes transaction details as input, preprocesses the data, and uses a pre-trained XGBoost machine learning model to predict whether the transaction is likely to be fraudulent.

## Features

*   **User-friendly Form:** A web form to input transaction details.
*   **Data Preprocessing:**  Transforms raw transaction data into features suitable for machine learning.
*   **Fraud Prediction:** Uses a pre-trained XGBoost model to predict fraud.
*   **Clear Results:** Displays the prediction result ("Fraud" or "Not Fraud").

## Technologies Used

*   Django
*   Scikit-learn
*   XGBoost
*   Pandas
*   Numpy
*   Geopy
*   Gunicorn

## Setup and Installation

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd CreditCardFraudDetection
    ```

2.  **Create a virtual environment:**

    ```bash
    python -m venv venv
    ```

3.  **Activate the virtual environment:**

    *   **Windows:**

        ```bash
        venv\Scripts\activate
        ```

    *   **macOS/Linux:**

        ```bash
        source venv/bin/activate
        ```

4.  **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

5.  **Set up the database:**

    ```bash
    python manage.py migrate
    ```

6.  **Run the development server:**

    ```bash
    python manage.py runserver
    ```

7.  **Access the application in your browser:**

    ```
    http://127.0.0.1:8000/
    ```

## Deployment

The project includes a `Procfile` for deployment to platforms like Heroku. Make sure you have the Heroku CLI installed.

1.  **Create a Heroku app:**

    ```bash
    heroku create
    ```

2.  **Deploy the application:**

    ```bash
    git push heroku main
    ```

3.  **Run migrations on Heroku:**

    ```bash
    heroku run python manage.py migrate
    ```

4.  **Set the `SECRET_KEY` environment variable in Heroku:**

    ```bash
    heroku config:set SECRET_KEY="your_secret_key"
    ```

5.  **Open the application in your browser:**

    ```bash
    heroku open
    ```

## Data Preprocessing Steps

The following data preprocessing steps are applied to the input transaction data:

*   **Data Cleaning:** Converts date and time columns to the correct data types.
*   **Credit Card Categorization:**  Categorizes credit card numbers based on card type (Visa, Mastercard, etc.).
*   **Age Calculation:** Calculates the age of the cardholder.
*   **Distance Calculation:** Calculates the distance between the cardholder's location and the merchant's location.
*   **Holiday Distance:** Calculates the number of days to the next holiday.
*   **Label Encoding:** Converts categorical features to numerical values.
*   **Column Dropping:** Removes unnecessary columns.

## Machine Learning Model

The project uses a pre-trained XGBoost model for fraud detection.  The model is serialized and stored in the `models/` directory.

## Contributing

Feel free to contribute to the project by submitting pull requests.