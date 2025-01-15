Visibility Prediction Using Regression Models

Description

This project focuses on predicting visibility distance based on climatic indicators using a regression-based machine learning approach. The goal is to leverage data-driven models to provide accurate predictions for visibility, considering factors such as temperature, humidity, wind speed, and pressure. Designed with robust data validation and preprocessing techniques, the project ensures high-quality inputs for training and prediction. The solution is deployable via Pivotal Web Services, enabling real-time predictions for clients.

Key Features:
	•	Comprehensive data validation to ensure input quality.
	•	Dynamic clustering for enhanced model training.
	•	Advanced machine learning algorithms (Decision Tree Regressor, XGBoost) for optimal predictions.
	•	Scalable deployment with Pivotal Web Services.

Table of Contents
	1.	Installation and Setup
	2.	How to Use
	3.	Technologies Used
	4.	Features and Workflow
	5.	Future Enhancements

Installation and Setup

Prerequisites

Ensure Python 3.7 or above is installed on your machine.

Steps
	1.	Clone the repository:

git clone <repository_url>


	2.	Navigate to the project directory:

cd visibility-prediction


	3.	Install dependencies:

pip install -r requirements.txt


	4.	Start the Flask server:

python main.py

How to Use
	1.	For Training:
	•	Place the training files and schema file in the appropriate folder.
	•	Run the training module to validate and process the data.
	•	Models are trained using cluster-specific algorithms and saved for future predictions.
	2.	For Predictions:
	•	Upload the prediction data files via the defined endpoint.
	•	The system validates the files and processes the data.
	•	Predictions are generated and saved in a CSV file, with the file location provided as a response.
	3.	Use tools like Postman to test the endpoints or integrate the model into other applications.

Technologies Used
	•	Programming Language: Python
	•	Libraries:
	•	Flask: For API development
	•	SQLAlchemy: For database management
	•	scikit-learn: For data preprocessing and modeling
	•	XGBoost: For regression modeling
	•	Pandas and NumPy: For data manipulation
	•	matplotlib: For visualizing clustering and training progress
	•	APScheduler: For task scheduling

Features and Workflow

Data Validation
	•	Validates file structure, column names, and data types using schema files.
	•	Segregates valid files into a “Good Data” folder and invalid ones into a “Bad Data” folder.

Model Training
	•	Preprocesses data by handling null values, scaling, and clustering using KMeans.
	•	Trains cluster-specific models with Decision Tree Regressor and XGBoost.
	•	Selects the best-performing model for each cluster based on R-squared scores.

Prediction
	•	Clusters prediction data using the pre-trained KMeans model.
	•	Generates predictions using cluster-specific models.
	•	Outputs predictions in a CSV file with original data labels.

Deployment
	•	Deployed using Pivotal Web Services with the following configuration:
	•	main.py: Entry point for Flask server.
	•	Procfile: Defines application start command.
	•	runtime.txt: Specifies Python version.
	•	manifest.yml: Contains Pivotal app configuration.

