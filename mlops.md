# gcp MLOps with Vertex AI

## Task 1. Prepare your environment
git clone https://github.com/GoogleCloudPlatform/data-science-on-gcp

cd ~/data-science-on-gcp/10_mlops

pip3 install google-cloud-aiplatform cloudml-hypertune kfp numpy tensorflow

## Task 2. Run a standalone model
cat model.py

export PROJECT_ID=$(gcloud info --format='value(config.project)')
export BUCKET_NAME=$PROJECT_ID-dsongcp
python3 model.py --bucket $BUCKET_NAME --develop

## Task 3. Develop and deploy model using Vertex AI
To develop and deploy a pipeline on Vertex AI, a training pipeline must do five things in code:

Load up a managed dataset in Vertex AI
Set up training infrastructure to run model.py
Train the model by invoking functions in model.py on the managed dataset
Find the endpoint to which to deploy the model
Deploy the model to the endpoint
In the startup-vm terminal, examine the train_on_vertexai.py script used to develop and deploy pipeline on Vertex AI:

cat train_on_vertexai.py

python3 train_on_vertexai.py --project $PROJECT_ID --bucket $BUCKET_NAME --develop --cpuonly --tfversion 2.6

## Task 4. Make predictions from the deployed model
cd ../09_vertexai
bash ./call_predict.sh
cd ../10_mlops

Output:

Using endpoint [https://us-central1-aiplatform.googleapis.com/]
4600611737312428032
Using endpoint [https://us-central1-prediction-aiplatform.googleapis.com/]
[[0.60023278], [0.747012496]]


python3 call_predict.py

Output:

Prediction(predictions=[[0.60023278], [0.747012496]], deployed_model_id='8618297593950109696', explanations=None)
