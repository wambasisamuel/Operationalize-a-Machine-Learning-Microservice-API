[![wambasisamuel](https://circleci.com/gh/wambasisamuel/Operationalize-a-Machine-Learning-Microservice-API.svg?style=svg)](https://app.circleci.com/pipelines/github/wambasisamuel/Operationalize-a-Machine-Learning-Microservice-API)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

### Instructions

Clone this repository - git clone https://github.com/wambasisamuel/Operationalize-a-Machine-Learning-Microservice-API.git && cd Operationalize-a-Machine-Learning-Microservice-API
make setup - create a Python virtual environment and source it  
make install - install the Python dependencies needed by the project  
./run_docker.sh - build the docker image and run the container for the prediction api  
./make_prediction.sh - test the prediction api  
./upload_docker.sh - upload the api image to dockerhub  
minikube start - start a local kubernetes cluster  
./run_kubernetes.sh - deploy the application on the Kubernetes cluster  
minikube delete - delete the local Kubernetes cluster  
circleci config validate - validate the CircleCI config file  

### Key Project Files

Dockerfile: Configuration file for creating a docker image for the application  
.circleci/config.yml: CircleCI configuration file for running the tests  
Makefile: Contains a set of commands to setup environment, run tests and run lints  
app.py: Python flask app that returns predictions about housing prices when requested using API calls  
run_docker.sh: Script to build and run docker image locally  
make_prediction.sh: Script for testing API request to the Flask app  
upload_docker.sh: Script to tag and upload docker image to docker hub  
run_kubernetes.sh: Script to setup and run app on kubernetes  