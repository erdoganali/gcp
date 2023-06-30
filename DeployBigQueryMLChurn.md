# gcp Deploy a BigQuery ML Customer Churn Classifier to Vertex AI for Online Predictions 

![image](https://cdn.qwiklabs.com/pkJ0xATamv62qQLq4yzUNpplBXLNAxeaKliuTn5TcLs%3D) 

This lab is inspired by and extends https://cloud.google.com/blog/topics/developers-practitioners/churn-prediction-game-developers-using-google-analytics-4-ga4-and-bigquery-ml 

## What you'll learn
Explore and preprocess a Google Analytics 4 data sample in BigQuery for machine learning.

Train a BigQuery ML XGBoost classifier to predict user churn on a mobile gaming application.

Tune a BigQuery ML XGBoost classifier using BigQuery ML hyperparameter tuning features.

Evaluate the performance of a BigQuery ML XGBoost classifier.

Explain your XGBoost model with BigQuery ML Explainable AI global feature attributions.

Generate batch predictions with your BigQuery ML XGBoost model.

Export a BigQuery ML XGBoost model to a Google Cloud Storage bucket.

Upload and deploy a BigQuery ML XGBoost model to a Vertex AI Prediction Endpoint for online predictions.

## Setup and requirements

Click Activate Cloud Shell Activate Cloud Shell icon at the top of the Google Cloud console.
When you are connected, you are already authenticated, and the project is set to your PROJECT_ID. The output contains a line that declares the PROJECT_ID for this session:

Your Cloud Platform project in this session is set to YOUR_PROJECT_ID
gcloud is the command-line tool for Google Cloud. It comes pre-installed on Cloud Shell and supports tab-completion.

(Optional) You can list the active account name with this command:

gcloud auth list
Copied!
Click Authorize.

Your output should now look like this:

Output:

ACTIVE: *
ACCOUNT: student-01-xxxxxxxxxxxx@qwiklabs.net
To set the active account, run:
    $ gcloud config set account `ACCOUNT`

## (Optional) You can list the project ID with this command:

gcloud config list project
Copied!
Output:

[core]
project = <project_ID>
Example output:

[core]
project = qwiklabs-gcp-44776a13dea667a6

## Task 1. Enable Google Cloud services
In Cloud Shell, use gcloud commands to enable the services used in the lab:
gcloud services enable \
  compute.googleapis.com \
  iam.googleapis.com \
  iamcredentials.googleapis.com \
  monitoring.googleapis.com \
  logging.googleapis.com \
  notebooks.googleapis.com \
  aiplatform.googleapis.com \
  bigquery.googleapis.com

## Clone the lab repository
cd
git clone https://github.com/GoogleCloudPlatform/training-data-analyst


Navigate to lab notebook
In your notebook, navigate to training-data-analyst > quests > vertex-ai > vertex-bqml, and open lab_exercise.ipynb.

Continue the lab in the notebook, and run each cell by clicking the Run (run button icon) icon at the top of the screen. Alternatively, you can execute the code in a cell with SHIFT + ENTER.
