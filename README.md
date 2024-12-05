Sepsis Prediction

This project aims to build a machine learning pipeline for predicting sepsis using clinical data. It leverages FastAPI for creating a web-based API to serve the machine learning models, providing a user-friendly interface for predictions.

Table of Contents

Overview

Features

Technologies Used

Setup and Installation

Usage

File Structure

Future Improvements

License

Overview

Sepsis is a life-threatening condition caused by the body's response to infection.

Early prediction and detection of sepsis can significantly improve patient outcomes. 

This project uses machine learning techniques to predict the likelihood of sepsis based on clinical data inputs.

The project includes:

Pre-trained machine learning models such as Decision Trees, KNN, Logistic Regression, and Random Forests.

A FastAPI-based backend to handle API requests and return model predictions.

A Python-based pipeline for preprocessing and managing clinical data.


Features

Multiple ML Models: Includes several machine learning models for prediction, providing flexibility and accuracy comparisons.

API Integration: FastAPI-powered RESTful API for serving predictions.

File Upload Support: Accepts .csv files as input for batch predictions.

Error Handling: Handles invalid inputs gracefully with descriptive error messages.


Technologies Used

Programming Language: Python 3.10+

Web Framework: FastAPI

Machine Learning Libraries:

Scikit-learn

Pandas

NumPy

API Server: Uvicorn

Version Control: Git

Deployment: Docker (optional)

Setup and Installation

Follow these steps to set up and run the project locally:

Clone the Repository

bash

git clone https://github.com/RKGyampoh/Sepsis_prediction.git

cd Sepsis_prediction

Create a Virtual Environment

bash

python -m venv venv

venv\Scripts\activate          # For Windows

Install Dependencies

bash

pip install -r requirement.txt

Run the API Navigate to the project root directory and run the FastAPI app:

bash

uvicorn app.mlapi:app --reload

Access the API Open your browser and navigate to http://127.0.0.1:8000/docs to access the interactive Swagger UI.

Usage

API Endpoints

GET /docs: Access the Swagger UI for API testing.

POST /predictor: Predict sepsis based on input data.

Example Input

json

{
  
  "model": "Logistic Regression",

  "file": "<Upload CSV file containing clinical data>"
  
}

Example Response

json

{

  "model_used": "Logistic Regression",
  
  "predictions": [0, 1, 0, 0]
}

File Structure

bash

Final project/
│

├── app/


│   ├── __pycache__/          # Cached Python files

│   ├── d_api.py              # Additional API endpoints

│   ├── mlapi.py              # Main FastAPI application

│   └── __init__.py           # Package initialization file

│

├── data/

│   ├── cleaned_test_set.csv  # Sample dataset for testing

│   ├── Patients_Files_Train.csv

│   └── Patients_Files_Test.csv

│

├── models/

│   ├── Decision Tree_pipeline.pkl  # Pre-trained Decision Tree model

│   ├── KNN_pipeline.pkl            # Pre-trained KNN model

│   ├── Logistic Regression_pipeline.pkl

│   └── Random Forest_pipeline.pkl

│

├── venv/                      # Python virtual environment

├── requirement.txt            # List of dependencies

├── Dockerfile                 # Docker configuration 

├── sepsis.ipynb               # Jupyter Notebook for data analysis

└── README.md                  # Project documentation

Future Improvements

Add more robust error handling for invalid inputs.

Integrate more advanced machine learning models such as neural networks.

Deploy the API using cloud platforms like AWS/GCP.

Develop a front-end interface for easier interaction.


License
This project is licensed under the MIT License. See the LICENSE file for details.
