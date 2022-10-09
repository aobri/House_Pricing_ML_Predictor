<!-- <include a CircleCI status badge, here> -->
[![CircleCI](https://dl.circleci.com/status-badge/img/gh/aobri/House_Pricing_ML_Predictor/tree/master.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/aobri/House_Pricing_ML_Predictor/tree/master)
[![CircleCI](https://dl.circleci.com/status-badge/img/gh/aobri/House_Pricing_ML_Predictor/tree/master.svg?style=shield)](https://dl.circleci.com/status-badge/redirect/gh/aobri/House_Pricing_ML_Predictor/tree/master)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). 


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

## Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

## Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

## Important Files & Folders: 
* **app.py**: contians the app logic to apply the model on inputs.
* **model_data**: contains the trained model joblib and the training data used in csv.
* **Dokcerfile**: outlines the image contents to containerize this app.
* **Makefile**: basic commands to simplify development tasks liek installing requirements and linting code. 
* **requirements.txt**: contains the python dependencies for this app to function.
* **run_docker.sh**: build Dockerfile into an image and runs the app as a docker container.
* **upload_docker.sh**: retags and pushes the image created by run_docker, 
  * note: you will need to add your own docker hub user Id!
* **run_kubernetes.sh**: using the dokcer hub image, creates a kubernetes pod and runs the app. 