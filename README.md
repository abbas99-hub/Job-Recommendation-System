# Job Recommendation System using Machine Learning
This repository contains the code and instructions to build a job recommendation system using machine learning. The system is designed to provide personalized job recommendations based on user preferences and historical job data. The data for this project is scraped from Glassdoor, and the system is deployed using the Azure cloud platform.

## Business Understanding
The goal of this project is to develop a job recommendation system that helps users find relevant job opportunities based on their preferences and historical data. By leveraging machine learning techniques, we aim to provide personalized recommendations that align with the user's skills, interests, and career goals. The system will take into account various factors such as job title, salary estimate, company rating, location, industry, and more to generate accurate recommendations.

## Data Scraping
To collect the necessary data for training our recommendation system, we will scrape job-related information from Glassdoor. The following columns will be extracted:

Job Title
Salary Estimate
Job Description
Rating
Company Name
Location
Headquarters
Size
Founded
Type of Ownership
Industry
Sector
Revenue
Competitors

## Feature Engineering
Once the data is collected, we will perform feature engineering to preprocess and transform the raw data into a suitable format for training our recommendation model. This step includes:

Handling Missing Data: Deal with missing values in the dataset by either imputing them or removing the corresponding rows/columns.
Encoding Categorical Variables: Convert categorical variables such as job title, location, industry, and sector into numerical representations using techniques like one-hot encoding or label encoding.
Feature Scaling: Normalize numerical features, such as salary estimate and company rating, to ensure they have a similar scale and prevent dominance of certain features in the model.

## Model Training
We will train a machine learning model using the preprocessed data to generate job recommendations. The specific model architecture and algorithms used will depend on the nature of the recommendation problem. Some potential models that can be explored include:

Collaborative Filtering: Build a recommendation model based on user-item interactions and similarities.
Content-Based Filtering: Develop a model that recommends jobs based on the features and characteristics of the job listings.
Hybrid Approaches: Combine collaborative filtering and content-based techniques to leverage the strengths of both approaches.

## Model Evaluation
After training the model, we will evaluate its performance using suitable evaluation metrics such as precision, recall, and accuracy. This step will help us assess how well the model predicts job recommendations and identify areas for improvement.

## Model Deployment using Azure Cloud
To make the job recommendation system accessible to users, we will deploy the model on the Azure cloud platform. The deployment process involves the following steps:

* Model Serialization: Serialize the trained model to a format compatible with the Azure cloud deployment.
* Model Containerization: Package the serialized model along with the necessary dependencies and environment specifications into a container using tools like Docker.
* Azure Container Registry: Create a container registry on Azure to store the model container and related artifacts securely.
* Azure Kubernetes Service (AKS): Deploy the model container as a scalable microservice using AKS, which provides orchestration and management capabilities.
* API Development: Develop an API that allows users to interact with the deployed model and request personalized job recommendations.
* Integration and Testing: Integrate the API with other components of the job recommendation system, and perform thorough testing to ensure its functionality and performance.
* Deployment Monitoring: Monitor the deployed model and API to track usage, performance metrics, and address any potential issues or errors.

## Usage
To use the job recommendation system, follow the instructions below:

* Clone this repository: git clone <repository-url>
* Install the required dependencies: pip install -r requirements.txt
* Execute the data scraping script: python scrape_glassdoor.py
* Perform feature engineering on the scraped data: python feature_engineering.py
* Train the job recommendation model: python train_model.py
* Evaluate the model performance: python evaluate_model.py
* Serialize and containerize the trained model: python serialize_model.py and docker build -t job-recommendation .
* Create an Azure Container Registry and push the container: az acr create --name job-recommendation-registry and docker push job-recommendation-registry.azurecr.io/job-recommendation
* Deploy the model on Azure Kubernetes Service (AKS): az aks create --resource-group job-recommendation-group --name job-recommendation-aks --node-count 2 and kubectl apply -f deployment.yaml
* Access the deployed job recommendation API and make requests to receive personalized recommendations.

#### Please feel free to contribute to this project by submitting pull requests or opening issues.
